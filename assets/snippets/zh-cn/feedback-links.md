{{- $repo := .Get "repo" -}}
{{- if not $repo -}}
  {{- errorf "include %q requires repo: %s" (.Get "file") .Position -}}
{{- end -}}
如果您有一般性的建议或疑问，可以在[讨论区](https://github.com/{{ $repo }}/discussions)提出。

如果您有针对性的错误报告或功能要求，可以在[问题区](https://github.com/{{ $repo }}/issues)提出。
