<script type="text/javascript" charset="utf-8">  
	MyValidator.init();  
	</script>
	<script type="text/javascript">
	var MyValidator = function() {  
    var handleSubmit = function(true) {  
        $('.form-horizontal').validate({  
            errorElement : 'span',  
            errorClass : 'help-block',  
            focusInvalid : false,  
            rules : {  
                bulletinName : {  
                    required : true  
                },  
                comment : {  
                    required : true  
                } 
            },  
         messages : {  
                bulletinName : {  
                    required : "请填写栏目名称"  
               },  
                comment : {  
                    required : "请填写栏目描述"  
                } 
            },  
 
            highlight : function(element) {  
                $(element).closest('.form-group').addClass('has-error');  
            },  
  
            success : function(label) {  
                label.closest('.form-group').removeClass('has-error');  
                label.remove();  
            },  
  
            errorPlacement : function(error, element) {  
                element.parent('div').append(error);  
           },  
  
            submitHandler : function(form) {  
               form.submit();  
            }  
        });  
  
        $('.form-horizontal input').keypress(function(e) {  
            if (e.which == 13) {                  
            if ($('.form-horizontal').validate().form()) {  
                    $('.form-horizontal').submit();  
                }  
                return false;  
            }  
        });  
    }  
    return {  
        init : function() {  
            handleSubmit();  
        }  
    };  
  
}();  
	
	</script> 
