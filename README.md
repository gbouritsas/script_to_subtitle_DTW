Description
=====================================

This code implements the dynamic time warping algorithm for aligning movie scripts to their corresponding subtitles. It was used in [1] as part of the text processing pipeline, slightly modifying the original version of the code.

**Acknowledgements**: The DTW method was introduced in [2] and [3] and the code was originally developed by Dr. Ivan Laptev and used in [4], [5] and [6]. We also thank Dr. Bojanowski for providing us with the original version of the code.

Usage
=====================================
To run this code you will need:
1. the subtitle file (named *\*.srt.txt*)
2. the script file (named *\*_for_parsing.txt*),
3.  the *\*_word_ids.mat* file, which assigns a word id to character offsets starting from the beginning of the script file. This file can be obtained by running the coreNLP tokenizer on the script file (this can be done through the text processing pipeline of [1]: https://github.com/gbouritsas/cvpr18_multimodal_weakly_supervised_learning/tree/master/text_processing)

Place the above files in a common folder. You will need to declare the name of the folder for each movie by modifying the global variables movies_folder and movies. The path for the files 2 and 3 regarding the movie *i* is defined as follows: *$movies_foler/$movies{i}/results_script/*, while the path for the file 1 regarding the movie *i* should be: *$movies_foler/$movies{i}/*. For example, for the movies used in [1] you should run:
```
global movies_folder;
movies_folder='/Users/giorgosmpouritsas/Documents/movies/';
global movies;
movies = {'BMI', 'CRA', 'DEP', 'GLA', 'LOR'};
```

Finally, run:

```
% Vector containing the frames per second (fps) of each video
fps=24.9997500025000 * ones(length(movies));
% the script-subtitle DTW algorithm
align_subs_script_all(movies ,1, fps);
```

You can find more details regarding the code in the README provided by Dr. Laptev (README_Laptev.txt). Exemplar data can be found in: .

License
=====================================
This code is released under the MIT license (refer to the LICENSE file for details).


References
=====================================
[1] G. Bouritsas, P. Koutras, A. Zlatintsi and P. Maragos. Multimodal Visual Concept Learning with Weakly Supervised Learning Techinques. CVPR 2018.

[2] M. Everingham, J. Sivic and A. Zisserman. "Hello! My name is... Buffy" - Automatic Naming of Characters in TV Video. BMVC 2006.

[3] J. Sivic, M. Everingham and A. Zisserman. "Who are you?" : Learning person specific classifiers from video. CVPR 2009.

[4] I. Laptev, M. Marszalek, C. Schmid and B. Rozenfeld. Learning realistic human actions from movies. CVPR 2008.

[5] M. Marszalek, I. Laptev and C. Schmid. Actions in context. CVPR 2009.

[6] P. Bojanowski, F. Bach, I. Laptev, J. Ponce, C. Schmid, and J. Sivic. Finding actors and actions in movies. ICCV 2013.
