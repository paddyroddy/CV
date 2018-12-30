# make sure scons finds tex executables
import os
import multiprocessing

# target and source
target='CV.pdf'
source='CV.tex'

# run in parallel
num_cpu = multiprocessing.cpu_count()
SetOption('num_jobs', num_cpu)
print("running with -j", GetOption('num_jobs'))
env = Environment(ENV=os.environ)
output = env.PDF(target=target, source=source)
# Add synctex
env.AppendUnique(PDFLATEXFLAGS='-synctex=1')
# make sure that the pdf is reloaded properly (e.g., in Skim)
env.Precious(output)
