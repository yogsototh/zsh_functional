# usage:
#
# $ baz() { print $1 | grep baz }
# $ filter baz titi bazaar biz
# bazaar
filter() {
  (($#<1)) && {
    {
      print -- "usage: filter func list"
      print 
      print -- "example:"
      print -- '    > baz(){print "$*" | grep baz}'
      print -- '    > filter baz titi bazaar biz'
      print -- '    bazaar'
    } >&2
    return 1
  }
  typeset f="$1 \"\$1\""; shift
  filterl "$f" "$@"
}

filterl() {
  typeset f="$1"; shift
  typeset x
  for x; filter_ "$x" "$f"
  return 0
}
filter_() {
  eval "$2" && print -- "$1"
}

### filtera ArithRelation Arg ...  # is shorthand for
### filter '(( ArithRelation ))' Arg ...

filtera() {
  typeset f="(( $1 ))"; shift
  filterl "$f" "$@"
}
