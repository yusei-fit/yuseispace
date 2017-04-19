##==users_table==

	### users_columns

	* name      :string
	* mail      :string
	* password  :string
	* member    :string
	* profile   :text
	* avator    :string

	### users_associations

	* has_many :prototypes
	* has_many :comments
	* has_many :likes

##==comments_table==

	### comments_columns
	* comment     :string
	* user        :references
	* prototype   :references

	### comments_associations
	* belongs_to :user
	* belongs_to :prototype


##==prototypes_table==

	### prototypes_columns

	* catchcopy     :text
	* concept       :string
	* user        :references


	### prototypes_associations

	* belongs_to :user
	* has_many :comments
	* has_many :likes
	* has_many :images


##==likes_table==

	### likes_columns

	* likes_number    :integer
	* user        :references
	* prototype   :references

	### likes_associations==

	* belongs_to :user
	* belongs_to :user

##==images_table==

	### images_columns

	* enum image_type: {main: 0, sub: 10}
	* prototype :references

	### images_associations

	* belongs_to :user







