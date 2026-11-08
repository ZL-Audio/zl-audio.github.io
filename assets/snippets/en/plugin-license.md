{{- $repo := .Get "repo" -}}
{{- if not $repo -}}
  {{- errorf "include %q requires repo: %s" (.Get "file") .Position -}}
{{- end -}}
{{- $plugin := .Get "plugin" -}}
{{- if not $plugin -}}
  {{- errorf "include %q requires plugin: %s" (.Get "file") .Position -}}
{{- end -}}
{{ $plugin }} is Free and Open-source. {{ $plugin }} is licensed under [AGPLv3](https://www.gnu.org/licenses/agpl-3.0.en.html), except for the [logo of ZL Audio](https://github.com/{{ $repo }}/blob/main/assets/zlaudio.svg) and the [logo of {{ $plugin }}](https://github.com/{{ $repo }}/blob/main/assets/logo.svg). You can obtain the corresponding source code at https://github.com/{{ $repo }} or https://gitee.com/{{ $repo }}.
