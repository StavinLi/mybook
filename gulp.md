\#\#\#\#\#\# 1.\[线上开源地址:https://github.com/StavinLi/gulp-v.git\]\(https://github.com/StavinLi/gulp-v.git\)

\`\`\`

\#克隆

git clone https://github.com/StavinLi/gulp-v.git

\`\`\`

\#\#\#\#\#\# 2.安装依赖

\`\`\`

npm install

\`\`\`

\#\#\#\#\#\# 3.修改node\_modules配置文件



\#\#\#\#\#\# 3.1 gulp-rev\index.js



\`\`\`

第135行 manifest\[originalFile\] = revisionedFile;

更新为: manifest\[originalFile\] = originalFile + '?v=' + file.revHash;

\`\`\`



\#\#\#\#\#\# 3.2 rev-path\index.js

\`\`\`

9行 return filename + '-' + hash + ext;

更新为: return filename + ext;

\`\`\`



\#\#\#\#\#\# 3.3 gulp-rev-collector\index.js



\`\`\`

40行 path.basename\(json\[key\]\).replace\(new RegExp\( opts.revSuffix \), '' \)

更新为:  path.basename\(json\[key\]\).split\('?'\)\[0\] 

\`\`\`

\`\`\`

第146\170行 regexp: new RegExp\( '\(\[\/\\\\\'"\]\)' + pattern, 'g' \),

更新为: regexp: new RegExp\( '\(\[\/\\\\\'"\]\)' + pattern+'\(\\?v=\\w{10}\)?', 'g' \),

\`\`\`

\#\#\#\#\# 4.配置静态文件路径\`gulp-v/gulpfile.js\`

\`\`\`

var cssSrc = '../static/s/css/\*\*/\*\*/\*.css', //css文件路径

    jsSrc = '../static/s/js/\*\*/\*\*/\*.js',//js文件路径

    jspSrc = '../ydc\_project/ydc\_web/src/main/webapp/WEB-INF/view/\*\*/\*\*/\*.jsp',//修改jsp文件路径

    jspSaveSrc = '../ydc\_project/ydc\_web/src/main/webapp/WEB-INF/view'//修改后jsp文件保存路径

\`\`\`

\#\#\#\#\# 5.运行\`gulp\`

\`\`\`

gulp dev

\`\`\`

