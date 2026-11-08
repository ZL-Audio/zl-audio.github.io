{{- $repo := .Get "repo" -}}
{{- if not $repo -}}
  {{- errorf "include %q requires repo: %s" (.Get "file") .Position -}}
{{- end -}}
{{ .Get "intro" | default "Available at" }} [here](https://github.com/ZL-Audio/ZLNightlyRelease/releases/tag/{{ path.Base $repo }}). Nightly releases contain new features and fixes that may change before the formal release. Not recommended for critical production work. If you have specific bug reports or feature requests, you can open an issue [here](https://github.com/{{ $repo }}/issues).
