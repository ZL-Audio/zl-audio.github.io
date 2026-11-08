{{- $repo := .Get "repo" -}}
{{- if not $repo -}}
  {{- errorf "include %q requires repo: %s" (.Get "file") .Position -}}
{{- end -}}
您可以在[GitHub发布页](https://github.com/{{ $repo }}/releases/latest)下载安装器或者使用下面的下载链接。请下载与您的{{ if eq (.Get "platform") "os" }}操作系统和架构{{ else }}芯片/架构{{ end }}对应的安装器。
