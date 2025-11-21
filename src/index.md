# What is YSH?

YSH is a modern shell language designed to fix the common problems that make traditional shell scripting difficult and error-prone.

## The Problem with Traditional Shell

If you've written bash scripts, you've probably encountered:

```bash
# Bash - confusing and error-prone
if [ "$x" -lt "$y" ]; then  # Why the spaces? Why quotes?
    echo "x is less"
fi

result=$(cat file.txt | grep "pattern" | awk '{print $2}')  # Useless cat?
for file in *.txt; do       # What if no files match?
    process "$file"          # What if filename has spaces?
done
```

**Common complaints:**
- Whitespace and quoting are confusing
- Error handling is off by default
- Syntax is inconsistent (`[ ]` vs `[[ ]]` vs `(( ))`)
- Variables are strings by default (no real data types)
- Hard to read and maintain

## The YSH Solution

YSH fixes these issues with modern, clean syntax:

```ysh
# YSH - clear and safe
if (x < y) {
    echo 'x is less'
}

var result = $(grep "pattern" file.txt | awk '{print $2}')
for file in *.txt {         # Empty glob = empty list (no error)
    process $file           # Safer word splitting
}
```

**What makes YSH better:**
- Python-like expressions: `if (x < y)` instead of `if [ $x -lt $y ]`
- Real data types: integers, lists, dictionaries
- Error handling on by default (errexit)
- Consistent, readable syntax
- Keeps shell's power for commands and pipelines

## Who Should Use YSH?

### Perfect for:
- **Python/JavaScript developers** who need to write shell scripts
- **System administrators** who want maintainable automation
- **Anyone** frustrated with bash's quirks


## What's Next?

Now that you understand what YSH is, let's get it installed and write your first script!

**Next:** [Installing YSH](./getting-started.md)