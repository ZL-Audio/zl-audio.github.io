{{- $repo := .Get "repo" -}}
{{- if not $repo -}}
  {{- errorf "include %q requires repo: %s" (.Get "file") .Position -}}
{{- end -}}
{{- $plugin := .Get "plugin" -}}
{{- if not $plugin -}}
  {{- errorf "include %q requires plugin: %s" (.Get "file") .Position -}}
{{- end -}}
{{ $plugin }} 是**自由开源**的软件。除了 [ZL Audio 标志](https://github.com/{{ $repo }}/blob/main/assets/zlaudio.svg) 和 [{{ $plugin }} 标志](https://github.com/{{ $repo }}/blob/main/assets/logo.svg)，{{ $plugin }} 按照 [AGPLv3](https://www.gnu.org/licenses/agpl-3.0.en.html) 进行许可。您可以在 https://github.com/{{ $repo }} 或者 https://gitee.com/{{ $repo }} 获得源码。
