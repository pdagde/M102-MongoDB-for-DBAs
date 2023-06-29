{
	"collMod": "nonfiction  db.runCommand(",
	"validator": {
		$jsonChema : {
			required : ['name','price'],
			properties : {
				name : {
					bsonType : "string",
					description : "name field is required as a string"
				},
				price : {
					bsonType : "number",
					description : "price field is required as a number"
				},
				auther : {
					bsonType : 'array',
					description : "must be array and it is required",
					items : {
						bsonType : 'object',
						required : ['name','email'],
						properties : {
							name:{
								bsonType : 'tring',
								"description" : "name required" 
							},
							mail : {
								bsonType : 'string',
								description : 'mail required'
							}
						}
 					}
				},
			    publisher : {
					bsonType : 'object',
					description : "publisher should be object",
					required : ["publisher Name", 'details'],
					properties : {
						publisher_name : {
							bsonType : 'string'
						},
						details : {
							bsonType : 'object',
							required : ['code','history'],
							properties : {
								code : {
									bsonType : 'string'
								},
								history : {
									bsonType : array,
									items : {
										bsonType : 'object',
										required : ['book','date'],
										properties : {
											book : {
												bsonType : 'string'
											}
											date : {
												bsonType : string
											}
										}
									}
								}
							}
						}
					}
				}	
			}
		}
	}
}
