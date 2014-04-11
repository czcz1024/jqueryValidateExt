可以通过编写一些额外的脚本，改变由jquery.validate.unobtrusive.js生成的默认验证设置  
<script src="~/Scripts/jquery.validate.js"></script>
<script src="~/Scripts/jquery.validate.unobtrusive.js"></script>
<script src="~/Scripts/jquery.validate.extends.js"></script>
<script>
    $(function() {
        $("form").setNewValidateOption("errorPlacement", function(old) {
            return function (err, ele) {
                old(err, ele);
                var container = err.data("unobtrusiveContainer");
                container.prepend("<span>x</span>");
            };
        });
    });
</script>
