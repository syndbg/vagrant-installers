hashicorp_modules = [
  'autotools',
  'build_essential',
  'download',
  'fpm',
  'homebrew',
  'libffi',
  'libyaml',
  'openssl',
  'params_lookup',
  'patch',
  'powershell',
  'readline',
  'ruby',
  'util',
  'vagrant',
  'vagrant_installer',
  'wget',
  'wix',
  'zlib',
]

hashicorp_modules.each do |module_name|
  # The options to pass for our module
  opts = {}

  # If the LOCAL environmental variable is set, then we load the Puppet
  # modules from a local path.
  if ENV["LOCAL"]
    opts[:path] = "../puppet-modules/modules/#{module_name}"
  else
    opts[:git] = "git://github.com/hashicorp/puppet-modules.git"
    opts[:ref] = "ace19bd91452ae25ed53ce09fdaab8ae15e163f3"
    opts[:path] = "modules/#{module_name}"
  end

  mod module_name, opts
end
