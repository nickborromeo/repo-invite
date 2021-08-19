 # frozen_string_literal: true
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

# more stuff cut out

