# Observability Working Group

Project for tracking the work of the Observability Working Group

## Current WG projects

- [Telemetry][]
- [OpenTelemetry][]

## Awesome BEAM Observability

The curated list of tools for monitoring, instrumenting, and tracing
applications that run on BEAM. Inspired by many of such lists over the GitHub.

### Blog posts

- [Logs and Metrics and Graphs, Oh My!](https://grafana.com/blog/2016/01/05/logs-and-metrics-and-graphs-oh-my/)
- [Operable software](https://ferd.ca/operable-software.html) by [@ferd](https://github.com/ferd)

### Logging

- [`lager`](https://github.com/erlang-lager/lager) - popular logging framework with broad features set
- [`logger`](http://www.erlang.org/doc/man/logger.html) - OTP 21+ built-in pluggable logger module
- [`Logger`](https://hexdocs.pm/logger/Logger.html) - Elixir's built-in pluggable logger module that in recent Elixir versions also synchronises with Erlang's `logger` module
- [`systemd`](https://hex.pm/packages/systemd) - library for integrating with systemd, it provides utilities for integrating with systemd's journal

### Metrics

#### Recommended

- [OpenTelemetry][] - implementation of CNCF [OpenTelemetry][ot-official] for Erlang and Elixir
- [Prometheus](https://github.com/deadtrickster/prometheus.erl) - Prometheus integration for Erlang
- [Telemetry][] - dynamic dispatcher for Erlang metrics and instrumentations
  * [Telemetry.Poller](https://github.com/beam-telemetry/telemetry_poller) - periodically gather measurements and publish them as Telemetry events
  * [Telemetry.Metrics](https://github.com/beam-telemetry/telemetry_metrics) - common interface for defining metrics based on :telemetry events.
    * [TelemetryMetricsStatsd](https://github.com/beam-telemetry/telemetry_metrics_statsd) - StatsD compatible Telemetry.Metrics reporter.
    * [TelemetryMetricsPrometheus](https://github.com/beam-telemetry/telemetry_metrics_prometheus) - Prometheus compatible Telemetry.Metrics reporter.
    * [TelemetryMetricsZabbix](https://github.com/lukaszsamson/telemetry_metrics_zabbix) - Zabbix compatible Telemetry.Metrics reporter.
    * [PromEx](https://github.com/akoutmos/prom_ex) - A library used to monitor your Elixir applications using telemetry, Prometheus and pre-packaged Grafana dashboards.
    * [`plug_telemetry_server_timings`](https://github.com/hauleth/plug_telemetry_server_timing) - add `telemetry` metrics to `plug` response as [`Server-Timing`][server-timing] header.

[server-timing]: https://w3c.github.io/server-timing/#the-server-timing-header-field

#### Other

- [beam_stats](https://github.com/xandkar/beam_stats) - Collect detailed VM metrics and send to arbitrary, plugable backends (StatsD and Graphite backends included).
- [Fluxter](https://github.com/lexmag/fluxter) - InfluxDB writer for Elixir
- [Statix](https://github.com/lexmag/statix) - fast and reliable Elixir client for StatsD-compatible servers with some DogStatsD extensions (namely tags)
- [vmstats](https://github.com/ferd/vmstats) - tiny Erlang app to generate information on the Erlang VM

#### Historical

Over the many years of Erlang and Elixir's existence many libraries for metric collection have been created. However, expectations for modern metric gathering and reporting has changed during this time. The follow libraries are still used and do their job well, but they lack features like tags that are important for adding additional dimensions to metrics, which gives the user more control over aggregation. See the Datadog article, [The Power of Tagged Metrics](https://www.datadoghq.com/blog/the-power-of-tagged-metrics/), for more on the importance of tagging metrics.

- [Elixometer](https://github.com/pinterest/elixometer) - thin Elixir wrapper over Exometer
- [Exometer](https://github.com/Feuerlabs/exometer_core) - Erlang instrumentation package
- [Folsom](https://github.com/folsom-project/folsom) - expose Erlang events as metrics
- [`metrics`](https://github.com/benoitc/erlang-metrics) - generic interface to to a different metrics systems in Erlang

[Telemetry]: https://github.com/beam-telemetry/telemetry

### Tracing

#### Recommended

- [OpenTelemetry][] - The combined effort of OpenTracing and OpenCensus communities. [OpenTelemetry][ot-official] is a CNCF project that will replace both OpenTracing and OpenCensus.

Or for vendor specific solutions see:

- [AppSignal](https://github.com/appsignal/appsignal-elixir) - AppSignal Elixir integration package for gathering metrics, errors, and traces
- [New Relic](https://github.com/newrelic/elixir_agent) - New Relic's Elixir agent supports metrics, errors and distributed tracing

#### Other Implementations

- [~~OpenCenus~~](https://github.com/census-instrumentation/opencensus-erlang) (**ON HOLD, see [OpenTelemetry][]**) - implementation of Google's [OpenCensus.io](https://opencensus.io) tracing and monitoring with broad range of integrations:
  * [Absinthe](https://github.com/opencensus-beam/opencensus_absinthe)
  * [DataDog APM & DogStatsD](https://github.com/opencensus-beam/opencensus_datadog)
  * [Elixir](https://github.com/opencensus-beam/opencensus_elixir)
  * [Elli](https://github.com/opencensus-beam/opencensus_elli)
  * [Google Reporter](https://github.com/opencensus-beam/oc_google_reporter)
  * [Honeycomb](https://github.com/opencensus-beam/opencensus_honeycomb)
  * [InfluxDB](https://github.com/opencensus-beam/opencensus_influxdb)
  * [Jaeger](https://github.com/opencensus-beam/opencensus-jaeger)
  * [Plug](https://github.com/opencensus-beam/opencensus_plug)
  * [Prometheus](https://github.com/opencensus-beam/prometheus)
  * [Telemetry](https://github.com/opencensus-beam/opencensus_telemetry)
- [Otter](https://github.com/Bluehouse-Technology/otter) - OpenTracing (**see [OpenTelemetry][]**) integration library for Erlang
- [~~Spandex~~](https://github.com/spandex-project/spandex) (**ON HOLD, see [OpenTelemetry][]**) - tracing library for Elixir which supports DataDog APM. Integrations:
  * [Ecto](https://github.com/spandex-project/spandex_ecto)
  * [Phoenix](https://github.com/spandex-project/spandex_phoenix)
- [tracelog](https://github.com/opencensus-beam/tracelog) - logging handler that can transform structured logs into distributed tracing spans (for now supports only OpenCensus backend library)

[OpenTelemetry]: https://github.com/open-telemetry/opentelemetry-erlang
[ot-official]: https://opentelemetry.io

### Error logging

- [Aibrakex](https://github.com/fazibear/airbrakex) - Elixir client for Airbrake
- [Bugsnag](https://github.com/jarednorman/bugsnag-elixir) - Elixir interface to Bugsnag API
- [Rollbar](https://github.com/ForzaElixir/rollbax) - exception tracking and logging from Elixir to Rollbar
- [Sentry](https://github.com/getsentry/sentry-elixir) - official Elixir SDK for Sentry.io

## License

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](LICENSE).
