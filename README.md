##users_table

	### users_columns
	| name | type |option|
	|:-----------|:-----------:|:-----------:|
	|name|:string||
	|member|:string||
	|profile|:text||
	|avator|:string||
	|works|:text||
	|likes_count|:integer||
	|comments_count|:integer||
	|prototypes_count|:integer||

	##### mail・passwordカラムはgem devise で生成します。

	### users_associations
	| association | model|option|
	|:-----------|:-----------:|:-----------:|
	|has_many|:prototypes||
	|has_many|:comments||
	|has_many|:likes||

##comments_table

	### comments_columns
	| name | type |option|
	|:-----------|:-----------:|:-----------:|
	|body| :string||
	| user |:references||
	|prototype |:references||

	### comments_associations
	| association | model|option|
	|:-----------|:-----------:|:-----------:|
	|belongs_to|:user|counter_cache: true|
	|belongs_to|:prototype|counter_cache: true|


##prototypes_table

	### prototypes_columns
	|name|type|option|
	|:-----------|:-----------:|:-----------:|
	|catchcopy|:text||
	|concept|:string ||
	|user|:references||
	|likes_count|:integer||
	|comments_count|:integer||


	### prototypes_associations
	| association | model|option|
	|:-----------|:-----------:|:-----------:|
	|belongs_to|:user|counter_cache :true|
	|has_many|:comments||
	|has_many|:likes||
	|has_many|:images||


##likes_table

	### likes_columns
	| name | type |option|
	|:-----------|:-----------:|:-----------:|
	|likes_number | :integer||
	|user | :references||
	|prototype| :references||

	### likes_associations
	| association | model|option|
	|:-----------|:-----------:|:-----------:|
	|belongs_to|:user|counter_cache: true|
	|belongs_to|:user|counter_cache: true|

##images_table

	### images_columns
	| name | type |option|
	|:-----------|:-----------:|:-----------:|
	|enum |image_type: {main: 0, sub: 1}||
	|prototype |:references||

	### images_associations
	| association | model|option|
	|:-----------|:-----------:|:-----------:|
	|belongs_to|:prototype||







