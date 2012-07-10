map() {
  (($#<1)) && {
    print -- "usage: map funcname [list]"
    print
    print -- 'example:'
    print -- '    > foo(){print "x: $1"}'
    print -- '    > map foo a b c d'
    print -- '    x: a'
    print -- '    x: b'
    print -- '    x: c'
    print -- '    x: d'
    return 1
  }
  local func_name=$1
  shift
  for elem in $@; print -- $(eval $func_name $elem)
}

mapl () {
  (($#<1)) && {
    print -- "usage: mapl lambda-function [list]"
    print
    print -- 'example:'
    print -- "    > mapl 'echo \"x: \$1\"' a b c d"
    print -- '    x: a'
    print -- '    x: b'
    print -- '    x: c'
    print -- '    x: d'
    return 1
  }
  typeset f="$1"; shift
  typeset x
  typeset result=0
  for x; mapl_ "$x" "$f" || result=$?
  return $result
}
mapl_ () {
  eval "${(e)2}"
}


mapa () {
  (($#<1)) && {
    print -- "usage: mapa lambda-arithmetic [list]"
    print -- "       (shorthand for mapl '$[ f ]' [list])"
    print
    print -- 'example:'
    print -- "    > mapa '\$1+5' {1..3}"
    print -- '    6'
    print -- '    7'
    print -- '    8'
    return 1
  }
  typeset f="\$[ $1 ]"; shift
  mapa__ "$f" "$@"
}

mapa__ () {
  (($#<1)) && return 1
  typeset f="$1"; shift
  typeset x
  typeset result=0
  for x; mapa_ "$x" "$f" || result=$?
  return $result
}

mapa_ () {
  print -- "${(e)2}"
}
