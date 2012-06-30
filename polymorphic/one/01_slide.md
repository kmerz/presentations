!SLIDE
# Ring of Polymorph Control #
A alternative to :polymorphic by

https://github.com/genua/polymorphic

!SLIDE bullets incremental
# Polymorph Trap #
	@@@ ruby
	class Dungeon < ActiveRecord::Base
	  has_many :monsters, :polymorphic => true
	end

!SLIDE
# You step on a polymorph trap #
	@@@ ruby
	level_one = Dungeon.new
	level_one.monster << Leech.create
	level_one.monster << Vampire.create
	level_one.monster << Fountain.create #WHAT???
	level_one.monster.save!
	level_one.monster.size # 3  REALLY??

!SLIDE
# Get the Ring of Polymorph Control #
	@@@ ruby
	require "polymorphic"
	class Dungeon < ActiveRecord::Base
	  has_and_belongs_to_many :leechs
	  has_and_belongs_to_many :vampires
	  polymorphic :monsters, :leechs, :vampires
	end

!SLIDE
# Use the Ring of Polymorph Control #
	@@@ ruby
	level_one = Dungeon.new
	level_one.monster << Leech.create
	level_one.monster << Vampire.create
	level_one.monster << Fountain.create #WHAT???
	level_one.monster.save!
	level_one.monster.size # 2    AHHH!!

!SLIDE bullets
# My character
* twitter: @k_merz
* github: http://github.com/kmerz
* company: www.genua.de
* company github: http://github.com/genua
* polymorphic: https://github.com/genua/polymorphic

