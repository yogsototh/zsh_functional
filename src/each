eachl() {
  typeset f="$1"; shift
  typeset x
  typeset result=0
  for x; each_ "$x" "$f" || result=$?
  return $result
}

each_() {
  eval "$2"
}

each() {
  typeset f="$1 \"\$1\""; shift
  eachl "$f" "$@"
}

