{{- $repo := .Get "repo" -}}
{{- if not $repo -}}
  {{- errorf "include %q requires repo: %s" (.Get "file") .Position -}}
{{- end -}}
You may download the installer at the [GitHub release page](https://github.com/{{ $repo }}/releases/latest) or use the direct download link below. Please download the installer that matches your {{ if eq (.Get "platform") "os" }}OS & architecture{{ else }}chip/architecture{{ end }}:
