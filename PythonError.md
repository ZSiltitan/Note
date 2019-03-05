#### doing dataframe logic comparison
1. 
    >>sla_final['origin_location'] == 'KOTA DENPASAR' & sla_final['SLA'] == 10
    TypeError: cannot compare a dtyped [int64] array with a scalar of type [bool]
	
	>>(sla_final['origin_location'] == 'KOTA DENPASAR') & (sla_final['SLA'] == 10)
	Works!!
	
This one is because **& has higher precedence than ==.**
