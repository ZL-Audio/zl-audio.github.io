{{- $repo := .Get "repo" -}}
{{- if not $repo -}}
  {{- errorf "include %q requires repo: %s" (.Get "file") .Position -}}
{{- end -}}
If you have general suggestions or questions, you can open a discussion [here](https://github.com/{{ $repo }}/discussions).

If you have specific bug reports or feature requests, you can open an issue [here](https://github.com/{{ $repo }}/issues).
