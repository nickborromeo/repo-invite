 # frozen_string_literal: true
# rubocop:disable Bundler/OrderedGems
# bootstrap version: v10 (rev to force rebundling on deploy / checkout)

# grpc and google-protobuf are very picky about their Ruby version
# and won't install on edge versions. We need this so we can compile
# Ruby from the master branch and bundle successfully.
if ENV["RUBY_NEXT"] || ENV["JANKY_ENV_RUBY_SHA"]
  module BundlerHack
    def __materialize__
      if name == "grpc" || name == "google-protobuf" || name == "nokogiri"
        Bundler.settings.temporary(force_ruby_platform: true) do
          super
        end
      else
        super
      end
    end
  end
  Bundler::LazySpecification.prepend(BundlerHack)
end

source "https://rubygems.org"

# Configure the gems that should not be cleaned out between bundles.
# This list is defined in `config/bundler_persistent_gems.rb` and includes:
# 1. Rails gems that change between Rails versions
# 2. Other libraries that change versions between Rails versions
require_relative "config/bundler_persistent_gems"
Bundler.settings.temporary(persistent_gems_after_clean: BUNDLER_PERSISTENT_GEMS_AFTER_CLEAN)

rails_version = "7.0.0.alpha.13a714f"

# Select Rails components to reduce unneeded dependencies
gem "actionmailer", rails_version
gem "actionpack", rails_version
gem "actionview", rails_version
gem "activejob", rails_version
gem "activemodel", rails_version
gem "activerecord", rails_version
gem "activesupport", rails_version
gem "railties", rails_version

gem "actionview_precompiler", "0.2.3.65.gc455f62"
gem "aleph-client",        "5.0.0.r1bee1cb2"
gem "allocation_sampler",  "1.0.0"
gem "acme-client",         "2.0.8"
gem "addressable",         "~> 2.3"
gem "argon2"
gem "asciidoctor",         "2.0.10.131.g4284a176"
gem "authnd-client",       "0.3.0.rd7283a13"
gem "authzd-client",       "0.10.1.reb952c33"
gem "aws-sdk-s3",          "~> 1"
gem "azure_key_vault",     "~> 0.18.0"
gem "azure_mgmt_compute",  "~> 0.21.1"
gem "azure_mgmt_key_vault", "~> 0.17.6"
gem "azure_mgmt_resources", "~> 0.18.0"
gem "azure-storage-blob",  "~> 1.1.0"
gem "bcrypt"
gem "bertrpc",             "1.3.1.github10"
gem "bert",                "1.1.10.49.gaa7e3f5"
gem "bindata",             "2.4.10"
gem "bootsnap",            "~> 1.7"
gem "braintree",           "~> 2.104"
gem "builder",             "3.2.3"
gem "cff",                 "0.8.0.17.g3f6c7ac"
gem "chatops-controller",  "4.1.0.18.ga5eedad"
gem "chatterbox-client",   "2.1.3.gd04a86a"
gem "charlock_holmes",     "0.7.7"
gem "chroma",              "~> 0.2.0"
gem "coconductor",         "~> 0.9"
gem "codeowners",          "0.0.1.r28439d5"
gem "color",               "1.8"
gem "committee",           "3.2.0"
gem "commonmarker",        "0.21.0.2.g91d4548"
gem "concurrent-ruby-ext"
gem "contentful",          "~> 2.16"
gem "creole",              "0.3.6"
gem "cuprite",             "0.11"
gem "cvss-suite",          "2.0.1"
gem "darrrr",              "0.1.6"
gem "diff-lcs",            "1.1.3"
gem "divvy",               "1.1.4.g677870a"
gem "dnsruby",             "1.61.5"
gem "dogstatsd-ruby",      "~> 4.1.0"
gem "dogapi",              "~> 1.28.0"
gem "driftwood-client",    "0.0.1.r35d9c04f"
gem "duo_api",             "1.0.1"
gem "earthsmoke",          "1.2.6"
gem "ecma-re-validator",   "~> 0.1"
gem "ed25519",             "~> 1.2"
gem "egress",              "0.0.8"
gem "email_reply_parser",  "0.5.10"
gem "elastomer-client",    "~> 3.2"
gem "escape_utils",        "1.2.1"
gem "ernicorn",            "1.0.3", :path => "vendor/internal-gems/ernicorn"
gem "eventer-client",      "0.4.2.g50ee773"
gem "excon",               "~>0.71"
gem "failbot",             "2.9.1"
gem "faker",               "~> 2.11.0"
gem "faraday",             "~> 0.17.0"
gem "fast_blank",          "1.0.0"
gem "fast_gettext",        "2.0.3"
gem "flipper",             "0.17.2"
gem "freno-client",        "~> 0.8.1"
gem "gemoji",              "4.0.0.rc3"
gem "geoip2_compat",       "0.0.3"
gem "geo_pattern",         "~> 1.2.1"
gem "get_process_mem",     "~> 0.2.7"
gem "geyser-client",       "0.20.0.rb8370f36"
gem "gettext",             ">=3.3.6", :require => false
gem "gettext_i18n_rails",  "1.8.1"
gem "gibbon",              "2.2.3"
gem "github-ds",           "0.5.2.2.g17e9bac"
gem "github-launch",       "0.0.1.r59566ad1d"
gem "github-linguist",     "7.16.1"
gem "github-markup",       "4.0.0"
gem "github-pages-health-check", "1.17.6"
gem "github-proto-repositories", "1.2.11.re9f78aa"
gem "github-proto-users",        "1.3.0.r47a1f7a"
gem "github-proto-auditlogs",    "0.0.1.gf480608"
gem "github-proto-support",      "1.1.1.r1d24950"
gem "github-proto-insights",  "1.0.1.rff71795"
gem "github-proto-octocat", "1.0.0.r07ac63f"
gem "monolith-twirp-billing-accounts", "1.8.0"
gem "monolith-twirp-classroom-integration", "1.0.2"
gem "monolith-twirp-classroom-users", "1.0.1"
gem "monolith-twirp-classroom-repositories", "1.0.6"
gem "monolith-twirp-classroom-classroom_repositories", "1.0.5"
gem "monolith-twirp-classroom-sync_classroom", "1.0.5"
gem "monolith-twirp-education_web-users", "1.1.1"
gem "monolith-twirp-features-core", "1.0.0"
gem "monolith-twirp-octoshift-imports", "1.9.1"
gem "monolith-twirp-actions-core", "1.0.22"
gem "monolith-twirp-authzd-enumerator", "1.0.1"
gem "monolith-twirp-auditlog-streaming", "1.1.0"
gem "monolith-twirp-mailreplies-replies", "1.0.0"
gem "monolith-twirp-notifications-notifyd", "1.1.0"
gem "monolith-twirp-octoshift-migrations", "1.1.5"
gem "monolith-twirp-support-helphub", "1.13.0"
gem "monolith-twirp-packageregistry-auditlog", "1.0.2"
gem "monolith-twirp-insights-auth", "1.2.1"
gem "monolith-twirp-insights-core", "1.1.0"
gem "monolith-twirp-conduit-feeds", "1.1.1"
gem "github_chatops_extensions", "0.0.8"
gem "gitrpc",              :path => "vendor/gitrpc"
gem "github-scout",       "0.1.1.r05ea5e5"
gem "google-api-client",   "~> 0.53"
gem "goomba",              "0.0.1.399.g354dff8"
gem "gpgme",               "~> 2.0"
gem "graphql",             "1.11.8"
gem "graphql-batch",       "0.4.3"
gem "graphql-client",      "0.16.0.52.g8fb3a8a"
gem "graphql-relay-walker", "0.3.0"
gem "graphql-schema_comparator", "1.0.0"
gem "group_syncer",        "1.6.5.re8320a7d"
gem "grpc",                "1.36.0"
gem "google-protobuf", "3.14.0.1.g1529d5f6e"
gem "googleapis-common-protos-types", "~> 1.0.1"
gem "hana",                "~> 1.3.6"
gem "hashids",             "1.0.5"
gem "homograph-detector",  "~> 0.1.1"
gem "horcrux",             "0.1.2"
gem "http_parser.rb",      "~> 0.5.2"
gem "inline_svg",          "1.3.1"
gem "iopromise",           "0.1.5"
gem "ipaddress"
gem "json5",               "0.0.1"
gem "jwt",                 "~> 2.1.0"
gem "json_schema",         "~> 0.20.0"
gem "kubeclient",          "4.9.1"
gem "levenshtein-ffi",     "~>1.1"
gem "lz4-ruby",            "~> 0.3.3"
gem "parallel"
gem "parser",              "~> 3.0.0"
gem "licensee",            "~> 9.10"
gem "liquid"
gem "lmdb",                "~> 0.4.8"
gem "lru_redux",           "0.8.4.14.g99d8d60"
gem "mail",                "~> 2.6"
gem "mapbox-sdk",          "2.3.0.9.g727cf07"
gem "memcached",           "1.8.0"
gem "mochilo",             "1.3.5.g70afb07"
gem "monetize",            "1.11.0"
gem "money-open-exchange-rates", "~> 1.3"
gem "monolith-twirp-examples-octocat", "1.0.1"
gem "money",               "~> 6.13.0"
gem "msgpack",             "~> 1.0"
gem "mustache",            "1.1.1"
gem "net-http-persistent", "~> 4.0.1"
gem "net-smtp",            "0.1.0.1.g0713b09"
gem "nokogiri",            ">= 1.11"
gem "notifyd-client",      "0.0.1.rc5b3bca"
gem "oauth2",              "~> 1.4.1"
gem "octolytics",          "0.18.0.1.gaf19991"
gem "octicons_helper",     "15.0.0"
gem "chunky_png",          "~> 1.3.0"
gem "optimizely-sdk",      "3.3.1"
gem "org-ruby",            "0.9.12"
gem "pathspec",            "~> 0.1.2"
gem "phonelib",            "~> 0.6.22"
gem "pinglish",            "0.2.1"
gem "posix-spawn",         "0.3.15"
gem "prawn",               "2.4.0"
gem "prawn-svg",           "0.32.0"
gem "prawn-table",         "0.2.2"
gem "prelude-batch-loader"
gem "premailer",           "1.13.1"
gem "presto-client",       "0.5.2"
gem "primer_view_components", "0.0.51"
gem "prometheus_exporter", "0.5.3", :require => false
gem "prose_diff",          "0.3.1"
gem "proto-dependency-graph-api", "1.0.0.ra91131ea"
gem "proto-dependabot-api", "0.0.11.rea2a3d47"
gem "proto-registry-metadata-api", "0.12.14.r0ccde24d"
gem "proto-registry-metadata-migrator-api", "0.1.2.r98615f6d"
gem "monolith-twirp-registrymetadata-core", "1.9.0"
gem "public_suffix",       "~> 4.0"
gem "rack",                "2.2.3"
gem "rack-bug",            "0.3.0"
gem "rails-controller-testing", "1.0.5"
gem "rake",                "13.0.1"
gem "rblineprof",          "0.3.7", :platforms => :mri
gem "rbnacl",              "~> 7.0"
gem "rbtrace",             "0.4.10", :platforms => :mri
gem "rdoc",                "6.2.1"
gem "RedCloth",            "4.3.2"
gem "redis",               "~> 4.0"
gem "resilient",           "~> 0.4.0"
gem "resque",              "1.20.0.74.g5be47e2"
gem "resqued",             "0.11.1"
gem "rich_text_renderer",  "~> 0.2.2"
gem "rinku",               "2.0.6"
gem "rollup",              "0.8.0"
gem "rotp",                "~> 6.2.0"
gem "rqrcode",             "0.10.1"
gem "ruby-progressbar",    "~>1.7", :require => false
gem "rubypants",           "0.2.0"
gem "safe_yaml",           "1.0.5"
gem "sass",                "3.7.4"
gem "sourcemap",           "0.1.1"
gem "sanitize",            "5.2.2"
gem "scientist",           "1.3.0"
gem "scrolls",             "0.9.1"
gem "secret-scanning-proto", "0.0.1.r7132fda"
gem "secure_headers",      "6.3.0"
gem "security-center-proto", "0.0.1.ra71e19c"
gem "ssh_data",            "1.1.0.24.g1c4cacb"
gem "simple_lockfile",     "~> 1.1.1"
gem "simple_uuid",         "~> 0.3.0"
gem "sinatra",             "2.0.8.1"
gem "slop",                "~> 3.4"
gem "spamurai-dev-kit",    "1.0.3"
gem "spokes-proto",        "0.0.1.ra5c7292"
gem "stackprof",           "0.2.17"
gem "statsd-ruby",         "0.3.0.github.3.38.gd478cc7"
gem "stripe",              "5.34.0"
gem "terminal-notifier",   "1.4.2"
gem "terminal-table",      "~>1.6.0"
gem "thread_safe",         "0.3.5.c8158c9"
gem "treelights-client",   "0.1.1.gf3f412d"
gem "trilogy",             "1.0.4"
gem "trilogy_adapter",     "1.0.4.r79bdd78"
gem "turboscan-client",    "1.0.0.r97904461"
gem "twilio-ruby",         "5.52.0"
gem "twirp",               "~> 1.1"
gem "unicorn",             "6.0.0"
gem "browser",             "5.1.0"
gem "venice",              "0.6.0"
gem "version_sorter",      "2.2.4"
gem "view_component",      "2.36.0"
gem "vintage-client",      "0.0.1.r233bca8"
gem "wcag_color_contrast", "~> 0.1.0"
gem "webauthn",            "~> 2.4.0"
gem "webpush",             "0.3.2"
gem "wikicloth",           "0.8.1.github5.2.g1bdbe36"
gem "will_paginate",       "~> 3.1"
gem "yajl-ruby",           "1.4.0.33.g7168bd7"
gem "hydro-client",        "0.3.1.174.g063a7b1"
gem "ruby-kafka",           "1.3.0"
gem "zuorest",             "2.5.2.5.g356f90e"
gem "zstd-ruby"
gem "aqueduct-client",     "0.1.2.rda87869"
gem "ipaddr",              "1.2.2"

gem "badge-ruler", "0.0.1"
gem "service-catalog-client", "0.7.0"

# OAuth
gem "omniauth", "~> 1.9"
gem "omniauth-oauth2", "~> 1.7"
# OmniAuth CSRF protection
gem "omniauth-rails_csrf_protection", "~> 0.1.2"

# enterprise specific gems go here for now
#
# NOTE: the `oa-enterprise` gem is built from the "0-3-stable" branch
#       of the https://github.com/github/omniauth repository
gem "github-ldap",   "1.10.1.20.g06d2c92"
gem "net-ldap",      "0.17"
gem "oa-enterprise", "0.3.2.g3930d46"
gem "octokit",       "~>4.3"
gem "xmldsig",       "0.4.1"

# Used for licenses on both GHES & GitHub.com (the latter for GitHub Connect)
gem "enterprise-crypto", "0.4.23"

# Billing API Gem
gem "billing-client", "1.1.1.r3c6fa43"

# OpenTelemetry Dependencies
gem "opentelemetry-sdk", "1.0.0.rc2"
gem "opentelemetry-exporter-otlp", "0.20.0"
gem "opentelemetry-instrumentation-faraday", "0.19.0"
gem "opentelemetry-instrumentation-graphql", "0.18.1"
gem "opentelemetry-instrumentation-rack", "0.19.0"
gem "opentelemetry-instrumentation-rails", "0.18.1"
gem "opentelemetry-propagator-ottrace", "0.19.0"
gem "github-telemetry", "0.9.0"
gem "opentelemetry-instrumentation-trilogy", "0.9.0"

group :development, :test do
  gem "arca",   "2.1.3", :require => false
  gem "factory_bot_rails", "~> 6.2"
  gem "guard", "~> 2.16", require: false
  gem "erb_lint", "0.1.0", require: false
  gem "guard-livereload", "~> 2.5", require: false
  gem "launchy"
  gem "packwerk", "~> 1.3"
  gem "pry"
  gem "byebug-dap", "~> 0.1.4"
  gem "pry-byebug", "~> 3.9"
  gem "break"
  gem "toxiproxy", "1.0.3"
  gem "webrick"
end

# these available outside of development for using AST parsing for script/generate-service-files.rb
gem "rubocop", "1.13.0", require: false
gem "rubocop-ast", require: false

group :development do
  gem "benchmark-ips", "2.8.2", :require => false
  gem "dotenv", "~> 2.7"
  gem "sshkey", "~> 1.3.2"
  gem "rubocop-github", "0.16.2", :require => false
  gem "rubocop-performance", "~> 1.11", :require => false
  gem "rubocop-rails", "~> 2.7", :require => false
  gem "rubocop-rspec", "~> 1.30", ">= 1.30.1", require: false
  gem "letter_opener",     "1.7.0"
  gem "solargraph", "~> 0.40.4", :require => false
end

group :test do
  gem "minitest", "~> 5.14.0"
  gem "minitest-stub-const", "0.6"
  gem "minitest-focus", "> 1.2.1"
  gem "html-proofer", "3.12.2"
  gem "mocha",             "1.1.0"
  gem "rack-test",         "0.6.3", :require => "rack/test"
  gem "timecop",           "0.9.1"
  gem "ladle",             "~> 1.0"
  gem "vcr",               "~> 5.0"
  gem "test-queue",        "0.4.2"
  # mock net:http requests for vcr (eg, braintree)
  gem "webmock",           "3.8.3.9.g382d84c"
  gem "capybara",          "3.10.0.660.g3e28cb90"
  gem "selenium-webdriver"
  gem "webdrivers"
  gem "licensed",          "~> 2.0"
  gem "zeus",              "~> 0.15.14", :require => false
  gem "simplecov",         "~> 0.21.2"
  gem "tcr",               "0.1.0"
  gem "pdf-reader", "2.2.0"
end
