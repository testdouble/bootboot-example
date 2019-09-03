source "https://rubygems.org"

plugin "bootboot"
Plugin.send(:load_plugin, "bootboot") if Plugin.installed?("bootboot")
Bundler.settings.set_local("bootboot_env_prefix", "RAILS")

if ENV["RAILS_NEXT"]
  enable_dual_booting if Plugin.installed?("bootboot")

  gem "rails", "~> 5.1.0"
else
  gem "rails", "~> 5.0.0"
end
