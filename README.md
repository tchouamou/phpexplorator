# phpexplorator
php web explorer
phpexplorator is a web interface to remote explore, manage, preview , edit, create, copy, rename, download, upload, zip, unzip ..etc, files, images, and directory in the server site. Integrated with TinyMce, useful for computer programmer and admin.

The Mini have the same code with the normal version but:
The mini version is not multi-language
The mini version don't include the Tinymce Editor

You need just to copy the [index.php] in your document root of your web browser.
You can also copy the [phpexplorator.class.php] in your document root and user the next code for your php script:


<?php
 include_once(phpexplorator.class.php");
 $p1 = new phpexplorator();
 $p1->show();
?>

Your can also add a config.php file in the same directory with the next variable

        $PE_config["authentification_need"] = "no"; //--(url, form, no, basic, apache, 0, 1)--if require authentification
        $PE_config["my_username"] = "admin"; //--username to be use (ex:admin)
        $PE_config["my_password"] = "admin"; //--password to be use (ex:admin)
        $PE_config["challenge_need"] = "1"; //--(0, 1)--if require challenge authentification
        $PE_config["begin_path"] = "./"; //--begin path
        $PE_config["path_limit"] = "all"; //--(all, www, begin_path)--1 to phpexplorator path limt
        $PE_config["user_policy"] = "admin"; //--(guest, admin) phpexplorator can write files
        $PE_config["cookie_alive"] = 3600; // time you want session to be mantain
        
        $PE_config["images_url"] = "images/icons/"; //--url to icon
        $PE_config["images_path"] = $PE_config["images_url"]; //--url to icon
        $PE_config["style_file"] = "style.css"; //--folder of icon
        
        $PE_config["lang_path"] = "./lang/"; //--folder of languages files
        $PE_config["self_header"] = "0"; //-- activate or disactivate phpexplorator  sending http image header
        $PE_config["PE_key"] = "cmr_mode";//-- optional var to be send (usefull when integrated in other application)
        $PE_config["PE_val"] = "explore";//-- optional var value to be send (usefull when integrated in other application)
        
        $PE_config["current_language"] = "default"; //--(italian, english, french, default)
        
        $PE_config["show_error"] = "0"; //--(0,1)--1 to show phpexplorator error
        $PE_config["date_format"] = "d-m-Y, H:i"; //--("Y-m-d, H:i:s")  phpexplorator date format
        $PE_config["max_num_files"] = 10000; //-- phpexplorator max num files to be elaborated
        $PE_config["personal_header"] = ""; //--phpexplorator personal header
        $PE_config["personal_footer"] = "  All rights reserved."; //-- phpexplorator personal footer
        
        $PE_config["show_title"] = "0"; //--(0,1)--1 to show phpexplorator title
        $PE_config["show_command_1"] = "1"; //--(0,1)--1 to show phpexplorator command_1
        $PE_config["show_command_2"] = "1"; //--(0,1)--1 to show phpexplorator command_2
        $PE_config["show_command"] = "1"; //--(0,1)--1 to show phpexplorator command
        $PE_config["show_command_upload"] = "1"; //--(0,1)--1 to show phpexplorator command_upload
        $PE_config["show_shell"] = "1"; //--(0,1)--1 to show phpexplorator shell
        $PE_config["show_email"] = "1";
        $PE_config["show_mysql"] = "1";
        $PE_config["show_replace"] = "1"; //--(0,1)--1 to show phpexplorator replace
        $PE_config["show_command_extend"] = "1"; //--(0,1)--1 to show phpexplorator command_extend
        $PE_config["show_head_dir"] = "1"; //--(0,1)--1 to show phpexplorator head_dir
        $PE_config["show_dir_list"] = "1"; //--(0,1)--1 to show phpexplorator dir_list
        $PE_config["show_footer"] = "1"; //--(0,1)--1 to show phpexplorator footer
        $PE_config["show_action"] = "1"; //--(0,1)--1 to run phpexplorator action
        
        $PE_config["beautifull_name"] = "0"; //--(0,1)--1 to show phpexplorator file name beautifully
        $PE_config["show_col_name"] = "1"; //--(0,1)--1 to show phpexplorator column name
        $PE_config["show_col_num"] = "1"; //--(0,1)--1 to show phpexplorator column num
        $PE_config["show_col_check"] = "1"; //--(0,1)--1 to show phpexplorator column check
        $PE_config["show_col_action"] = "1"; //--(0,1)--1 to show phpexplorator column action
        $PE_config["show_col_comment"] = "1"; //--(0,1)--1 to show phpexplorator column comment
        $PE_config["show_col_size"] = "1"; //--(0,1)--1 to show phpexplorator column size
        $PE_config["show_col_type"] = "1"; //--(0,1)--1 to show phpexplorator column type
        $PE_config["show_col_perm"] = "1"; //--(0,1)--1 to show phpexplorator column permission
        $PE_config["show_col_owner"] = "1"; //--(0,1)--1 to show phpexplorator column owner
        $PE_config["show_col_group"] = "1"; //--(0,1)--1 to show phpexplorator column group
        $PE_config["show_col_date_time"] = "1"; //--(0,1)--1 to show phpexplorator column date_time
        
        $PE_config["use_extend_editor"] = "0"; //--(0,1)--good editor but slow
        $PE_config["editor_compression"] = "0"; //--(0,1)--good to be fast but don't work all time
        $PE_config["editor_compression_language"] = "php"; //--(php, jsp, aspx, cfm)
        $PE_config["tinymce_path"] = ""; //--folder of tinymce files
        $PE_config["tinymce_php_file"] = "./tinymce/jscripts/tiny_mce/tiny_mce_gzip_php.js"; //--tinymce files need for php compression
        $PE_config["tinymce_jsp_file"] = "./tinymce/jscripts/tiny_mce/tiny_mce_gzip_jsp.js"; //--tinymce files need for jsp compression
        $PE_config["tinymce_aspx_file"] = "./tinymce/jscripts/tiny_mce/tiny_mce_gzip_aspx.js"; //--tinymce files need for aspx compression
        $PE_config["tinymce_cfm_file"] = "./tinymce/jscripts/tiny_mce/tiny_mce_gzip_cfm.js"; //--tinymce files need for cfm compression
        $PE_config["tinymce_js_file"] = "./tinymce/jscripts/tiny_mce/tiny_mce_gzip.js"; //--tinymce files need compression
  