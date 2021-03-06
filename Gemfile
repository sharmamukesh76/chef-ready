#
# Copyright:: Copyright (c) 2014-2016 Chef Software Inc.
# License:: Apache License, Version 2.0
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#

source "https://rubygems.org"

gemspec

gem "bundler"

group(:omnibus_package, :development, :test) do
  gem "rake"
  gem "pry"
  gem "rdoc"
  gem "yard"
  gem "guard"
  gem "cookstyle", ">= 2.0.0"
  gem "foodcritic", ">= 12.1"
  gem "ffi-libarchive"
end

group(:dep_selector) do
  gem "dep_selector"
  gem "dep-selector-libgecode"
end

# We tend to track latest stable release without pinning.
# In order to prevent the depsolver from downgrading we pin some floors with ">=".
# We should only be using "~>" to work around bugs, or temporarily pinning some tech debt.
# We equality pin the chef gem itself to assert which version we're shipping.
group(:omnibus_package) do
  gem "appbundler"
  gem "berkshelf", ">= 7.0"
  gem "chef-provisioning", ">= 2.7.1", group: :provisioning
  gem "chef-provisioning-aws", ">= 3.0.2", group: :provisioning
  gem "chef-provisioning-fog", ">= 0.26.1", group: :provisioning
  gem "chef-vault", ">= 3.3.0"
  gem "chef", "= 14.3.37"
  gem "cheffish", ">= 14.0.1"
  gem "chefspec", ">= 7.2.0"
  gem "fauxhai", ">= 5.4.0"
  gem "inspec", ">= 2.1.68"
  gem "kitchen-ec2", ">= 2.2.1"
  gem "kitchen-digitalocean", ">= 0.9.8"
  gem "kitchen-dokken", ">= 2.6.7"
  gem "kitchen-google", ">= 1.4.0"
  gem "kitchen-hyperv", ">= 0.5.1"
  gem "kitchen-inspec", ">= 0.19.0"
  gem "kitchen-vagrant", ">= 1.3.2"
  gem "knife-acl", ">= 1.0.3"
  gem "knife-ec2", ">= 0.15.0"
  gem "knife-google", ">= 3.2.0"
  gem "knife-tidy", ">= 0.2.1"
  gem "knife-windows", ">= 1.9.0"
  gem "knife-opc", ">= 0.3.2"
  gem "knife-vsphere", ">= 2.0.3"
  gem "mixlib-archive", "= 0.4.6" # FIXME: equality pinned for now because windows is busted on 0.4.7
  gem "ohai", ">= 14.0.29"
  gem "net-ssh", ">= 4.2.0"
  gem "test-kitchen", ">= 1.21.1"
  gem "listen"
  gem "dco"

  # For Delivery build node
  gem "chef-sugar"
  gem "mixlib-versioning"
  gem "artifactory"
  gem "opscode-pushy-client", ">= 2.4.11"
  gem "ffi-rzmq-core"
  gem "knife-push"

  # All of the following used to be software definitions we included:
  gem "knife-spork"
  gem "mixlib-install"
  gem "nokogiri"
  gem "pry-byebug"
  gem "pry-remote"
  gem "pry-stack_explorer"
  gem "rb-readline"
  gem "rubocop"
  gem "winrm-fs"
  gem "winrm-elevated"
  gem "cucumber"
  gem "stove"
end

# Everything except AIX
group(:ruby_prof) do
  gem "ruby-prof"
end

# Everything except AIX and Windows
group(:ruby_shadow) do
  gem "ruby-shadow", platform: :ruby
end

gem "chefstyle", group: :test

# TODO delete this when we figure out how to include the pushy windows dependencies
# correctly
platforms :mswin, :mingw do
  gem "rdp-ruby-wmi"
  gem "windows-api"
  gem "windows-pr"
  gem "win32-api"
  gem "win32-dir"
  gem "win32-event"
  gem "win32-mutex"
  gem "win32-process", "~> 0.8.2"
  gem "win32-service"
end
