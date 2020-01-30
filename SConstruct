# -*- coding: utf-8 -*-
"""
Main SConstruct file
"""
import os
import os.path

targets = map(str, BUILD_TARGETS)

import docsassembler as docs

#----------------------Body------   ---------------------
EnsurePythonVersion(2, 7)
EnsureSConsVersion(1, 2, 0)
#SetOption('implicit_cache', 1)
SetOption('max_drift', 1)
#SetOption('num_jobs', 2)  


env = docs.DocstructEnvironment(r"c:\app\docstruct", ENV = os.environ )
env['ENV']['PATH'] = os.environ['PATH']

env.Decider('timestamp-match')
docs.write_project_path()

taskCleanObj = os.path.join(os.getcwd(), '--obj/cleanObj') 
cmd = env.Command(taskCleanObj, [], [docs.clean_obj])
env.Alias('clean-obj', cmd)


targets = map(str, BUILD_TARGETS)
for filename in targets:
    if filename.endswith(".pdf"):
        env.meta_analyzer.register_pdf(filename)
     
   
print "BUILD_TARGETS is", map(str, BUILD_TARGETS)

targets = map(str, BUILD_TARGETS)


