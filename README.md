Balatro/  源码根目录
┣ engine/ 不是LOVE2d引擎，而是作者从别的游戏里剽窃来的代码。作为开发的基础。
┃ ┣ animatedsprite.lua  应该主要提供的是类似tween的能力
┃ ┣ controller.lua  hover、点击等操作响应逻辑，还有些overlay menu字样的代码
┃ ┣ event.lua  事件类、事件管理类，里面有队列之类的；
┃ ┣ http_manager.lua  应该主要是网络相关的，代码量很少
┃ ┣ moveable.lua  node子类，有align、draw、drag、set vt、juice up（猛动）、move、glue等方法（game object已经包含了）
┃ ┣ node.lua  object子类，应该类似ccnode，UI可能基于node
┃ ┣ object.lua  实现面向对象的基础类
┃ ┣ particles.lua   实现粒子基类
┃ ┣ profile.lua   应该是profiler方面的，不是玩家profile
┃ ┣ save_manager.lua  存档相关
┃ ┣ sound_manager.lua  声音相关
┃ ┣ sprite.lua  movable子类，有个draw shader方法比较重要
┃ ┣ string_packer.lua  没看
┃ ┣ text.lua  DynaText，有update、draw等方法
┃ ┗ ui.lua  uibox和uielement都是movable子类，有calculate_xywh，有group，有检测点击、hover等
┣ functions/  应该是静态函数，定义的东西都形如G.FUNCS.tut_next = function(e) ...
┃ ┣ button_callbacks.lua  各种按钮的点击回调函数，加检测回调函数比如can_open, HUD_blind_visible
┃ ┣ common_events.lua  ease_hand,add_joker等，很多都调用G.E_MANAGER:add_event(Event({。也有大量的重要逻辑，比如generate card ui, create_card，有近3000行。
┃ ┣ misc_functions.lua  杂项
┃ ┣ state_events.lua   游戏状态有关事件，例如end round、G.FUNCS.play_cards_from_highlighted。里面有很多事件触发事件的“套娃”
┃ ┣ test_functions.lua  几个测试函数，do action、 play video等；
┃ ┗ UI_definitions.lua  UI配置。有create_UIBox_debug_tools，create_UIBox_win等。其中有些create函数里面套了其他create ui函数
┣ localization/ 里面存的是各种文本的本地化版本，有文本变量在里面，例如“在{C:attention}小盲注{}或{C:attention}大盲注{}被选中时”
┃ ┣ de.lua
┃ ┣ en-us.lua
┃ ┣ es_419.lua
┃ ┣ es_ES.lua
┃ ┣ fr.lua
┃ ┣ id.lua
┃ ┣ it.lua
┃ ┣ ja.lua
┃ ┣ ko.lua
┃ ┣ nl.lua
┃ ┣ pl.lua
┃ ┣ pt_BR.lua
┃ ┣ ru.lua
┃ ┣ zh_CN.lua
┃ ┗ zh_TW.lua
┣ resources/  各种资源，美术、声音、shader等
┃ ┣ fonts/  字体
┃ ┃ ┣ GoNotoCJKCore.ttf
┃ ┃ ┣ GoNotoCurrent-Bold.ttf
┃ ┃ ┣ m6x11plus.ttf
┃ ┃ ┣ NotoSans-Bold.ttf
┃ ┃ ┣ NotoSansJP-Bold.ttf
┃ ┃ ┣ NotoSansKR-Bold.ttf
┃ ┃ ┣ NotoSansSC-Bold.ttf
┃ ┃ ┗ NotoSansTC-Bold.ttf
┃ ┣ shaders/  着色器
┃ ┃ ┣ background.fs
┃ ┃ ┣ booster.fs
┃ ┃ ┣ CRT.fs
┃ ┃ ┣ debuff.fs
┃ ┃ ┣ dissolve.fs  消融
┃ ┃ ┣ flame.fs
┃ ┃ ┣ flash.fs
┃ ┃ ┣ foil.fs
┃ ┃ ┣ gold_seal.fs
┃ ┃ ┣ holo.fs
┃ ┃ ┣ hologram.fs  应该是一种牌
┃ ┃ ┣ negative.fs
┃ ┃ ┣ negative_shine.fs
┃ ┃ ┣ played.fs
┃ ┃ ┣ polychrome.fs   多彩标签的牌使用
┃ ┃ ┣ skew.fs
┃ ┃ ┣ splash.fs   漩涡状动画
┃ ┃ ┣ vortex.fs
┃ ┃ ┗ voucher.fs  优惠券
┃ ┣ sounds/  游戏声音
┃ ┃ ┣ ambientFire1.ogg
┃ ┃ ┣ ambientFire2.ogg
┃ ┃ ┣ ambientFire3.ogg
┃ ┃ ┣ ambientOrgan1.ogg
┃ ┃ ┣ button.ogg  按钮
┃ ┃ ┣ cancel.ogg  取消
┃ ┃ ┣ card1.ogg  不知道card1代表什么
┃ ┃ ┣ card3.ogg
┃ ┃ ┣ cardFan2.ogg
┃ ┃ ┣ cardSlide1.ogg
┃ ┃ ┣ cardSlide2.ogg
┃ ┃ ┣ chips1.ogg
┃ ┃ ┣ chips2.ogg
┃ ┃ ┣ coin1.ogg  获得金币
┃ ┃ ┣ coin2.ogg
┃ ┃ ┣ coin3.ogg
┃ ┃ ┣ coin4.ogg
┃ ┃ ┣ coin5.ogg
┃ ┃ ┣ coin6.ogg
┃ ┃ ┣ coin7.ogg
┃ ┃ ┣ crumple1.ogg
┃ ┃ ┣ crumple2.ogg
┃ ┃ ┣ crumple3.ogg
┃ ┃ ┣ crumple4.ogg
┃ ┃ ┣ crumple5.ogg
┃ ┃ ┣ crumpleLong1.ogg
┃ ┃ ┣ crumpleLong2.ogg
┃ ┃ ┣ explosion1.ogg
┃ ┃ ┣ explosion_buildup1.ogg
┃ ┃ ┣ explosion_release1.ogg
┃ ┃ ┣ foil1.ogg
┃ ┃ ┣ foil2.ogg
┃ ┃ ┣ generic1.ogg
┃ ┃ ┣ glass1.ogg  玻璃牌
┃ ┃ ┣ glass2.ogg
┃ ┃ ┣ glass3.ogg
┃ ┃ ┣ glass4.ogg
┃ ┃ ┣ glass5.ogg
┃ ┃ ┣ glass6.ogg
┃ ┃ ┣ gold_seal.ogg
┃ ┃ ┣ gong.ogg
┃ ┃ ┣ highlight1.ogg
┃ ┃ ┣ highlight2.ogg
┃ ┃ ┣ holo1.ogg
┃ ┃ ┣ introPad1.ogg
┃ ┃ ┣ magic_crumple.ogg
┃ ┃ ┣ magic_crumple2.ogg
┃ ┃ ┣ magic_crumple3.ogg
┃ ┃ ┣ multhit1.ogg
┃ ┃ ┣ multhit2.ogg
┃ ┃ ┣ music1.ogg
┃ ┃ ┣ music2.ogg
┃ ┃ ┣ music3.ogg
┃ ┃ ┣ music4.ogg
┃ ┃ ┣ music5.ogg
┃ ┃ ┣ negative.ogg
┃ ┃ ┣ other1.ogg
┃ ┃ ┣ paper1.ogg
┃ ┃ ┣ polychrome1.ogg
┃ ┃ ┣ slice1.ogg
┃ ┃ ┣ splash_buildup.ogg
┃ ┃ ┣ tarot1.ogg  塔罗牌
┃ ┃ ┣ tarot2.ogg
┃ ┃ ┣ timpani.ogg
┃ ┃ ┣ voice1.ogg
┃ ┃ ┣ voice10.ogg
┃ ┃ ┣ voice11.ogg
┃ ┃ ┣ voice2.ogg
┃ ┃ ┣ voice3.ogg
┃ ┃ ┣ voice4.ogg
┃ ┃ ┣ voice5.ogg
┃ ┃ ┣ voice6.ogg
┃ ┃ ┣ voice7.ogg
┃ ┃ ┣ voice8.ogg
┃ ┃ ┣ voice9.ogg
┃ ┃ ┣ whoosh.ogg
┃ ┃ ┣ whoosh1.ogg
┃ ┃ ┣ whoosh2.ogg
┃ ┃ ┣ whoosh_long.ogg
┃ ┃ ┗ win.ogg
┃ ┣ textures/  贴图
┃ ┃ ┣ 1x/  小图
┃ ┃ ┃ ┣ 8BitDeck.png
┃ ┃ ┃ ┣ 8BitDeck_opt2.png
┃ ┃ ┃ ┣ balatro.png  题图，用在splash等地方
┃ ┃ ┃ ┣ balatro_alt.png
┃ ┃ ┃ ┣ BlindChips.png  
┃ ┃ ┃ ┣ boosters.png
┃ ┃ ┃ ┣ chips.png  筹码
┃ ┃ ┃ ┣ Enhancers.png
┃ ┃ ┃ ┣ gamepad_ui.png
┃ ┃ ┃ ┣ icons.png
┃ ┃ ┃ ┣ Jokers.png  各种小丑
┃ ┃ ┃ ┣ localthunk-logo.png
┃ ┃ ┃ ┣ playstack-logo.png
┃ ┃ ┃ ┣ ShopSignAnimation.png
┃ ┃ ┃ ┣ stickers.png
┃ ┃ ┃ ┣ tags.png
┃ ┃ ┃ ┣ Tarots.png  各种塔罗牌
┃ ┃ ┃ ┣ ui_assets.png  UI所用
┃ ┃ ┃ ┣ ui_assets_opt2.png
┃ ┃ ┃ ┗ Vouchers.png  优惠券所用
┃ ┃ ┗ 2x/  大图版本
┃ ┃   ┣ 8BitDeck.png
┃ ┃   ┣ 8BitDeck_opt2.png
┃ ┃   ┣ balatro.png
┃ ┃   ┣ balatro_alt.png
┃ ┃   ┣ BlindChips.png
┃ ┃   ┣ boosters.png
┃ ┃   ┣ chips.png
┃ ┃   ┣ Enhancers.png
┃ ┃   ┣ gamepad_ui.png
┃ ┃   ┣ icons.png
┃ ┃   ┣ Jokers.png
┃ ┃   ┣ localthunk-logo.png
┃ ┃   ┣ playstack-logo.png
┃ ┃   ┣ ShopSignAnimation.png
┃ ┃   ┣ stickers.png
┃ ┃   ┣ tags.png
┃ ┃   ┣ Tarots.png
┃ ┃   ┣ ui_assets.png
┃ ┃   ┣ ui_assets_opt2.png
┃ ┃   ┗ Vouchers.png
┃ ┗ gamecontrollerdb.txt  # Game Controller DB for SDL in 2.0.16 format
┣ back.lua  直译是“卡背”，指的基本上是牌组、套牌。例如绿色套牌+1出牌次数，等离子牌会先平均筹码和倍数，后做乘法分数计算
┣ blind.lua  直译是“盲注”，其实就是小关卡。一次大的旅程是run，一次小关卡就是blind
┣ card.lua  卡牌。各种卡都在里面，小丑牌、人头牌、数字牌、幻灵牌、塔罗牌、星球牌，有很多内容，7000行左右
┣ cardarea.lua  卡牌区域，比如弃牌堆、手牌区、未摸牌堆等
┣ card_character.lua  其实就是jimbo，用来跟玩家说话的一个小助手样的牌，在输赢、tutorial里都会出现
┣ challenges.lua  应该就是steam的成就
┣ conf.lua  很短的几个小配置，minWidth等。
┣ game.lua  游戏全局的很多东西，比如加载设置、初始化。可能控制了生命周期。
┣ globals.lua  做了很多全局变量的初始化，比如上面的G.FUNCS，G等等
┣ main.lua  LOVE引擎要求的入口文件，只有薄薄的一层，各种函数基本都被G承接了。
┣ tag.lua  跳过盲注时可以获得的“标签”
┗ version.jkr  简单的版本号