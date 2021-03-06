# VIM Distribution

This is a basic distribution of vim plugins and tools intended to be run
on top of the latest MacVIM snapshot.

We (Carl and Yehuda) both use this distribution for our own use, and
welcome patches and contributions to help make it an effective way to
get started with vim and then use it productively for years to come.

At present, we are still learning to use vim ourselves, so you should
anticipate a period of rapid development while we get a handle on the
best tools for the job. So far, we have mostly integrated existing
plugins and tools, and we anticipate to continue doing so while also
writing our own plugins as appropriate.

In general, you can expect that the tools we use work well together and
that we have given careful thought to the experience of using MacVIM
with the tools in question. If you run into an issue using it, please
report an issue to the issue tracker.


## Pre-requisites

The distribution is designed to work with Vim >= 7.3.

* Python 2.7
* pyflakes

## Commands

Commands | Descriptions
--- | ---
`<C-w>, <tab> or ,w` | Navege via viewports
`:cd <path>` | Open path */path*
`,x`, `,w` or `SHIFT+o` | Next buffer navegate
`,z`, `,q` or `SHIFT+p` | previous buffer navegate
`,e` | Find and open files
`,b` | Find file on buffer (open file)
`,d` | Close active buffer (clone file)
`\b <0-9>` | Open buffer number
`tn` | Create new empty buffer
`\d`, `\n` or `F3`  | Open/Close three navegate files
`\f` | List all class and method
`\j` | Go to the method stated
`\v` or `Ctrl+w + v` | Split vertical
`\h` or `Ctrl+w + h` | Split horizontal
`Ctrl + k` | Open interactive python console
`\sh` | Open bash in *vim*
`,o` | Open github file/line (website), if used git in **github**
`\ga` | git add **.**
`\gc` | git commit -m
`\gsh` | git push
`\gs` | git status
`\gd` | git diff
`\gr` | git remove
`\\w` | EasyMotion word mode
`\\f{char}` | EasyMotion character mode
`W, E or B` | navigate through words considering case, underscores and others
`html path then C-Y,` | Emmet html mounting. Examples here: http://mattn.github.io/emmet-vim/#howworkthis
`\l` | Calls [howdoi](https://github.com/laurentgoudet/vim-howdoi) plugin

## Installation

    curl https://raw.github.com/avelino/.vimrc/master/bootstrap.sh -o - | sh

## Updating to the latest version

    :BundleUpdate

## Make Speller on VIM (ex: pt-br)
*Recommendad for person who uses vim for text written*

We will use the package translation of truth (lib LibreOffice to Portuguese):

	mkdir /var/tmp/vero
	cd /var/tmp/vero
    wget http://extensions.libreoffice.org/extension-center/vero-verificador-ortografico-e-hifenizador-em-portugues-do-brasil/pscreleasefolder.2012-01-04.1563120832/2.1/vero_pt_br_v210aoc.oxt
	unzip -x vero_pt_br_v210aoc.oxt

Next step is generate dictionary:

	vim

On vim run:

	:mkspell pt pt_BR 

Always press enter to continue!

Add dictionary on core vim:

	sudo cp /var/tmp/vero/pt.utf-8.spl /usr/share/vim/vim*/spell/ 


### Commands

Commands | Descriptions
--- | ---
`]s` | next word
`[s` | prev word
`z=` | open sugestion list
`zg` | add word on dictionary
`zug` | undoes add word of dictionary
`zw` | remove word on dictionary
`zuw` | undoes remove word on dictionary
