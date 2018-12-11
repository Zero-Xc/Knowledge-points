case                           
	when F.CODE is null 
		then  d.code                                    
	else			
		f.code
	end as 子件料号  	     
		 
	                                  
                                    
cast(g.price as decimal(24,9)) as 厂商平均价1,  
--CAST (expression AS data_type)
cast(h.price as nvarchar(50))  as 厂商平均价2,  
--将expression转型为data_type(data_type可以是任意类型，比如nvarchar)
decimal(24,9)      
--精度与小数位数分别为24与9。精度是总的数字位数，包括小数点左边和右边位数的总和。                   
--这表示本例能够支持的最大的整数值是999999999999999 （15位），而最小的小数值是0.000000001（9位）
													

--cast里面嵌套了case ..end (作为一个sql表达式)  
cast(case                               
	when d11.DescFlexField_PrivateDescSeg4='' 
		then 0.00     
	else
		d11.DescFlexField_PrivateDescSeg4 
	end as decimal(24,9)) as 损耗率1
			  
              
CONVERT(data_type(length),data_to_be_converted,style)               
data_type(length) 规定目标数据类型（带有可选的长度）,  
data_to_be_converted 含有需要转换的值,  
style 规定日期/时间的输出格式(有表)。  
	
CONVERT() 函数可以用不同的格式显示日期/时间数据。  
CONVERT(VARCHAR(11), GETDATE(), 23)             --GETDATE() 函数从 SQL Server 返回当前的时间和日期。

UNION 操作符用于合并两个或多个 SELECT 语句的结果集。  
请注意，UNION 内部的 SELECT 语句必须拥有相同数量的列。列也必须拥有相似的数据类型。同时，每条 SELECT 语句中的列的顺序必须相同。  
默认地，UNION 操作符选取不同的值。如果允许重复的值，请使用 UNION ALL。  

charindex ( expressionToFind , expressionToSearch  ,start_location)  
expressionToFind ：目标字符串，就是想要找到的字符串，最大长度为8000。  
expressionToSearch ：用于被查找的字符串。  
start_location：开始查找的位置，为空时默认从第一位开始查找。  
例子：select charindex('test','this Test is Test',7)    结果：14  
