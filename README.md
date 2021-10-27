# devops-netology

Из-за файла .gitignore внутри папки terraform исключаются:
1. все файлы с расширением .tfstate, .tfvars, .terraformrc
2. файлы crash.log, override.tf, override.tf.json, terraform.rc
3. файлы шаблона *_override.tf, *_override.tf.json, *.tfstate.*
4. внутренние директории .terraform с вложением