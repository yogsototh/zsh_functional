fold () {
  if (($#<2)) {
    {
    print -- 'usage: fold function list'
    print 
    print -- 'example:'
    print -- '    > bar() { print $(($1 + $2)) }' 
    print -- '    > fold bar 0 1 2 3 4 5' 
    print -- '    15'
    } >&2
    return 1
  } else {
    typeset f="\$($1 \$acc \$1)"; shift
    foldlp "$f" "$@"
  }
}

foldl () {
  if (($#<2)) {
    {
    print -- 'Warning, l is not for left! Its for lambda style expression!'
    print -- 'Though this is left fold still :)'
    } >&2
    return 1
  } else {
    local body=$1
    local acc=$2
    shift 2
    for x; acc=$(folde_ $x $acc $body)
    print -- $acc
    return 0
  }
}

folda () {
  typeset f="\$[ $1 ]"; shift
  foldlp "$f" "$@"
}

foldlp () {
  if (($#<2)) {
    {
    print -- 'Warning, l is not for left! Its for lambda style expression!'
    print -- 'Though this is left fold still :)'
    } >&2
    return 1
  } else {
    local body=$1
    local acc=$2
    shift 2
    for x; acc=$(fold_ $x $acc $body)
    print -- $acc
    return 0
  }
}

fold_ () {
  local acc=$2
  local body=$3
  print "${(e)body}"
}
folde_ () {
  local acc=$2
  local body=$3
  eval "${(e)body}"
}
