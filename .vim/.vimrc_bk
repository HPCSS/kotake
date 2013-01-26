filetype on "ファイル形式の検出の有効化
filetype indent on "インデントが有効になる
filetype plugin on "プラグインの有効化
syntax on

" NeoComplCache
"let g:neocomplcache_enable_at_startup = 1
let g:neocomplcache_enable_smart_case = 1
let g:neocomplcache_enable_camel_case_completion = 1

set autoindent

set number " 行数表示
"set nonumber "行数非表示

set expandtab "tabの代わりに空白文字の挿入

set shiftwidth=2 

"set tabstop=2 "tabの空白文字数
set softtabstop=2 "autoindent時のタブ挿入の幅

"改行の表示
"set list

"imap <C-o> <C-x><C-o>

" 全角スペースのハイライト
if has("syntax")
   syntax on
    function! ActivateInvisibleIndicator()
        syntax match InvisibleJISX0208Space "　" display containedin=ALL
        highlight InvisibleJISX0208Space term=underline ctermbg=Blue guibg=Blue
       "syntax match InvisibleTrailedSpace "[ \t]\+$" display containedin=ALL
       "highlight InvisibleTrailedSpace term=underline ctermbg=Red guibg=Red
       "syntax match InvisibleTab "\t" display containedin=ALL
       "highlight InvisibleTab term=underline ctermbg=Cyan guibg=Cyan
    endf


    augroup invisible
        autocmd! invisible
        autocmd BufNew,BufRead * call ActivateInvisibleIndicator()
    augroup END
endif

au BufNewFile,BufRead *.cl set filetype=cpp

"<TAB>で補完
"{{{Autocompletion using the TAB key
"This function determines, wether we are on the start of the line text (then
"tab indents) or 
"of we want to try autocompletion
function! InsertTabWrapper()
  let col = col('.') - 1
  if !col || getline('.')[col - 1]!~'\k'
    return "\<TAB>"
  else
    if pumvisible()
      return "\<C-N>"
    else
      return "\<C-N>\<C-P>"
    end
  endif
endfunction
"Remap the tab key to select action with InsertTabWrapper
"inoremap <tab> <c-r>=InsertTabWrapper()<cr>
"}}} Autocompletion using the TAB key

colorscheme opencl 
