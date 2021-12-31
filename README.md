// ==UserScript==
// @name         Lizy's Spells
// @namespace    http://tampermonkey.net/
// @version
// @author       JessTheVampire
// @match        https://www.bondageprojects.elementfx.com/*/BondageClub/
// @match        https://www.bondage-europe.com/R72/BondageClub/
// @grant        none
// ==/UserScript==



(function() {
    'use strict';

    //changing various parts of the game's code by replacing entire functions with altered ones
    function main() {

        ChatRoomActionMessage = function(msg, target = undefined) {
            if(msg.indexOf('/slime') == 0){
                //targetting do not change
                var who = parseInt(msg.substring(msg.indexOf(" ")))
                var char = ChatRoomCharacter[who-1]
//slime
                //Effect Of Spell
                InventoryWear(char, "SeamlessHobbleSkirt","ItemLegs")
                InventoryWear(char, "LatexBoxtieLeotard","ItemArms")
                InventoryGet(char, "ItemLegs").Color = '#9D40BF'
                InventoryGet(char, "ItemArms").Color = '#992AC2'
                InventorySetDifficulty(char, "ItemLegs", 99);
                InventorySetDifficulty(char, "ItemArms", 99);

                ServerPlayerInventorySync(char);
                ChatRoomCharacterUpdate(char);
                msg = Player.Name + ' casts slime on '+ char.Name+ '.'
            } else if(msg.indexOf('/safeword')==0){
                var who = parseInt(msg.substring(msg.indexOf(" ")))
                var char = ChatRoomCharacter[who-1]

//Safeword

                InventoryRemove(Player, "ItemVulva");
                InventoryRemove(Player, "ItemVulvaPiercings");
                InventoryRemove(Player, "ItemButt");
                InventoryRemove(Player, "ItemNipples");
                InventoryRemove(Player, "ItemNipplesPiercings");
                InventoryRemove(Player, "ItemBreast");
                InventoryRemove(Player, "ItemTorso");
                InventoryRemove(Player, "ItemPelvis");
                InventoryRemove(Player, "ItemNeckRestraints");
                CharacterRelease(Player)
                ChatRoomCharacterUpdate(Player);
                msg = Player.Name + ' completely shatters her binds to shreds.'
            } else if(msg.indexOf('/doll')==0){
                var who = parseInt(msg.substring(msg.indexOf(" ")))
                var char = ChatRoomCharacter[who-1]
//Doll

                InventoryRemove(char,'Bra',true)
                CurrentCharacter;
                InventoryRemove(char,'Panties',true)
                CurrentCharacter;
                InventoryRemove(char,'Shoes',true)
                CurrentCharacter;
                InventoryRemove(char,'Cloth',true)
                CurrentCharacter;
                InventoryRemove(char,'ClothLower',true)
                CurrentCharacter;

                InventoryWear(char, "Catsuit", "Suit")
                InventoryWear(char, "Catsuit", "SuitLower")
                InventoryWear(char, "TheDisplayFrame", "ItemDevices")
                InventoryWear(char, "LatexSocks1", "Socks")
                InventoryWear(char, "PaddedLeatherMittens", "ItemHands")
                InventoryWear(char, "StrictPostureCollar", "ItemNeck")
                InventoryWear(char, "FullBlindfold", "ItemHead")
                InventoryWear(char, "HeavyLatexCorset", "ItemTorso")
                InventoryWear(char, "WandBelt", "ItemVulva")
                InventoryWear(char, "ClothStuffing", "ItemMouth")
                InventoryWear(char, "HarnessBallGag", "ItemMouth2")
                InventoryWear(char, "LatexPostureCollar", "ItemMouth3")

                InventoryGet(char, "Suit").Color = ['#480E0D','#141414']
                InventoryGet(char, "SuitLower").Color = ['#480E0D','#141414']
                InventoryGet(char, "ItemDevices").Color = '#272727'
                InventoryGet(char, "Socks").Color = '#313131'
                InventoryGet(char, "ItemHands").Color = '#232323'
                InventoryGet(char, "ItemNeck").Color = '#575757'
                InventoryGet(char, "ItemTorso").Color = '#313131'
                InventoryGet(char, "ItemVulva").Color = ['#222222','#141414']
                InventoryGet(char, "ItemMouth3").Color = '#272727'
                InventoryGet(char, "ItemDevices").Color = '#272727'

                InventorySetDifficulty(Player, "ItemHead", 99);
                InventorySetDifficulty(Player, "ItemMouth3", 99);
                InventorySetDifficulty(Player, "ItemNeck", 99);
                InventorySetDifficulty(Player, "ItemTorso", 99);
                InventorySetDifficulty(Player, "ItemArms", 99);
                InventorySetDifficulty(Player, "ItemHands", 99);
                InventorySetDifficulty(Player, "ItemVulva", 99);
                InventorySetDifficulty(Player, "ItemMisc", 99);

                ChatRoomCharacterUpdate(char);

                msg = Player.Name + ' snaps her fingers unleashing her demonic power, encasing '+ char.Name+ ' in a dark and red dollsuit of steel and leather.'
            } else if(msg.indexOf('/web')==0){
                var who = parseInt(msg.substring(msg.indexOf(" ")))
                var char = ChatRoomCharacter[who-1]

//Web

                InventoryRemove(char,'Bra',true)
                CurrentCharacter;
                InventoryRemove(char,'Panties',true)
                CurrentCharacter;
                InventoryRemove(char,'Shoes',true)
                CurrentCharacter;
                InventoryRemove(char,'Cloth',true)
                CurrentCharacter;
                InventoryRemove(char,'ClothLower',true)
                CurrentCharacter;

                InventoryWear(char, "Tentacles", "ItemLegs")
                InventoryWear(char, "Tentacles", "ItemFeet")
                InventoryWear(char, "Tentacles", "ItemButt")
                InventoryWear(char, "Tentacles", "ItemArms")
                InventoryWear(char, "Tentacles", "ItemHead")
                InventoryWear(char, "Tentacles", "ItemMouth")

                InventoryGet(char, "ItemHead").Color = ['#131414']
                InventoryGet(char, "ItemFeet").Color = ['#CACCD4','#931717','#131414']
                InventoryGet(char, "ItemLegs").Color = ['#CACCD4','#931717','#131414']
                InventoryGet(char, "ItemArms").Color = ['#CACCD4','#931717','#131414']
                InventoryGet(char, "ItemButt").Color = ['#CACCD4','#931717','#131414']
                InventoryGet(char, "ItemMouth").Color = ['#131414']

                InventorySetDifficulty(Player, "ItemHead", 99);
                InventorySetDifficulty(Player, "ItemFeet", 99);
                InventorySetDifficulty(Player, "ItemMouth", 99);
                InventorySetDifficulty(Player, "ItemTorso", 99);
                InventorySetDifficulty(Player, "ItemArms", 99);


                ChatRoomCharacterUpdate(char);

                msg = Player.Name + ' aims her finger towards '+ char.Name+ ', entangling '+ char.Name+ ' in her tentacles, quickly binding the girl.,stripping her down in the process'
            } else if(msg.indexOf('/web')==0){
                var who = parseInt(msg.substring(msg.indexOf(" ")))
                var char = ChatRoomCharacter[who-1]
            }




// ALL SPELLS ABOVE THIS BRACKET......
            if (msg != "")
                ServerSend("ChatRoomChat",
                           { Content: "Beep", Type: "Action", Dictionary: [{ Tag: "Beep", Text: "msg" },
                                                                           { Tag: "Biep", Text: "msg" }, { Tag: "Sonner", Text: "msg" },
                                                                           { Tag: "msg", Text: msg }], Target: target });
        }


        ChatRoomSendChat =  function() {

            // If there's a message to send
            var msg = ElementValue("InputChat").trim()
            if (msg != "") {

                // Keeps the chat log in memory so it can be accessed with pageup/pagedown
                ChatRoomLastMessage.push(msg);
                ChatRoomLastMessageIndex = ChatRoomLastMessage.length;

                var m = msg.toLowerCase().trim();


                // Some custom functions like /dice or /coin are implemented for randomness
                if (m.indexOf("/dice") == 0) {

                    // The player can roll X dice of Y faces, using XdY.  If no size is specified, a 6 sided dice is assumed
                    if (/(^\d+)[dD](\d+$)/.test(msg.substring(5, 50).trim())) {
                        var Roll = /(^\d+)[dD](\d+$)/.exec((msg.substring(5, 50).trim()));
                        var DiceNumber = (!Roll) ? 1 : parseInt(Roll[1]);
                        var DiceSize = (!Roll) ? 6 : parseInt(Roll[2]);
                        if ((DiceNumber < 1) || (DiceNumber > 100)) DiceNumber = 1;
                    }
                    else if (/(^\d+$)/.test((msg.substring(5, 50).trim()))) {
                        var Roll = /(^\d+)/.exec((msg.substring(5, 50).trim()));
                        var DiceNumber = 1;
                        var DiceSize = (!Roll) ? 6 : parseInt(Roll[1]);
                    }
                    else DiceNumber = 0;

                    // If there's at least one dice to roll
                    if (DiceNumber > 0) {
                        if ((DiceSize < 2) || (DiceSize > 100)) DiceSize = 6;
                        var CurrentRoll = 0;
                        var Result = [];
                        var Total = 0;
                        while (CurrentRoll < DiceNumber) {
                            var Roll = Math.floor(Math.random() * DiceSize) + 1
                            Result.push(Roll);
                            Total += Roll;
                            CurrentRoll++;
                        }
                        msg = "ActionDice";
                        var Dictionary = [];
                        Dictionary.push({ Tag: "SourceCharacter", Text: Player.Name });
                        Dictionary.push({ Tag: "DiceType", Text: DiceNumber.toString() + "D" + DiceSize.toString() });
                        if (DiceNumber > 1) {
                            Result.sort((a, b) => a - b);
                            Dictionary.push({ Tag: "DiceResult", Text: Result.toString() + " = " + Total.toString() });
                        }
                        else if (DiceNumber == 1) Dictionary.push({ Tag: "DiceResult", Text: Total.toString() });
                        if (msg != "") ServerSend("ChatRoomChat", { Content: msg, Type: "Action", Dictionary: Dictionary });
                    }

                } else if (m.indexOf("/coin") == 0) {

                    // The player can flip a coin, heads or tails are 50/50
                    msg = "ActionCoin";
                    var Heads = (Math.random() >= 0.5);
                    var Dictionary = [];
                    Dictionary.push({ Tag: "SourceCharacter", Text: Player.Name });
                    Dictionary.push({ Tag: "CoinResult", TextToLookUp: Heads ? "Heads" : "Tails" });
                    if (msg != "") ServerSend("ChatRoomChat", { Content: msg, Type: "Action", Dictionary: Dictionary });

                } else if ((m.indexOf("*") == 0) || (m.indexOf("/me ") == 0) || (m.indexOf("/action ") == 0)) {


                    // The player can emote an action using * or /me (for those IRC or Skype users), it doesn't garble
                    // The command /action or ** does not add the player's name to it
                    msg = msg.replace("*", "");
                    msg = msg.replace(/\/me /g, "");
                    msg = msg.replace(/\/action /g, "*");
                    if (msg != "") ServerSend("ChatRoomChat", { Content: msg, Type: "Emote" });

                }
                else if (m.indexOf("/help") == 0) ServerSend("ChatRoomChat", { Content: "ChatRoomHelp", Type: "Action", Target: Player.MemberNumber});
                else if (m.indexOf("/safeword") == 0) ChatRoomSafewordChatCommand();
                else if (m.indexOf("/friendlistadd ") == 0) ChatRoomListManipulation(Player.FriendList, null, msg);
                else if (m.indexOf("/friendlistremove ") == 0) ChatRoomListManipulation(null, Player.FriendList, msg);
                else if (m.indexOf("/ghostadd ") == 0) { ChatRoomListManipulation(Player.GhostList, null, msg); ChatRoomListManipulation(Player.BlackList, Player.WhiteList, msg); }
                else if (m.indexOf("/do") == 0) {ChatRoomActionMessage(msg.substring(msg.indexOf(" ")).trim());console.log('action attempt')}
                else if (m.indexOf("/ghostremove ") == 0) { ChatRoomListManipulation(null, Player.GhostList, msg); ChatRoomListManipulation(null, Player.BlackList, msg); }
                else if (m.indexOf("/whitelistadd ") == 0) ChatRoomListManipulation(Player.WhiteList, Player.BlackList, msg);
                else if (m.indexOf("/whitelistremove ") == 0) ChatRoomListManipulation(null, Player.WhiteList, msg);
                else if (m.indexOf("/blacklistadd ") == 0) ChatRoomListManipulation(Player.BlackList, Player.WhiteList, msg);
                else if (m.indexOf("/blacklistremove ") == 0) ChatRoomListManipulation(null, Player.BlackList, msg);
                else if (m.indexOf("/ban ") == 0) ChatRoomAdminChatAction("Ban", msg);
                else if (m.indexOf("/unban ") == 0) ChatRoomAdminChatAction("Unban", msg);
                else if (m.indexOf("/kick ") == 0) ChatRoomAdminChatAction("Kick", msg);
                else if (m.indexOf("/promote ") == 0) ChatRoomAdminChatAction("Promote", msg);
                else if (m.indexOf("/demote ") == 0) ChatRoomAdminChatAction("Demote", msg);
                else if (m.indexOf("/afk") == 0) CharacterSetFacialExpression(Player, "Emoticon", "Afk");
                else if (msg != "" && !((ChatRoomTargetMemberNumber != null || m.indexOf("(") >= 0) && Player.ImmersionSettings && Player.ImmersionSettings.BlockGaggedOOC && !Player.CanTalk())) {
                    if (ChatRoomTargetMemberNumber == null) {
                        // Regular chat
                        ServerSend("ChatRoomChat", { Content: msg, Type: "Chat" });
                    } else {
                        // The whispers get sent to the server and shown on the client directly
                        ServerSend("ChatRoomChat", { Content: msg, Type: "Whisper", Target: ChatRoomTargetMemberNumber });
                        var TargetName = "";
                        for (let C = 0; C < ChatRoomCharacter.length; C++)
                            if (ChatRoomTargetMemberNumber == ChatRoomCharacter[C].MemberNumber)
                                TargetName = ChatRoomCharacter[C].Name;

                        var div = document.createElement("div");
                        div.setAttribute('class', 'ChatMessage ChatMessageWhisper');
                        div.setAttribute('data-time', ChatRoomCurrentTime());
                        div.setAttribute('data-sender', Player.MemberNumber.toString());
                        div.innerHTML = TextGet("WhisperTo") + " " + TargetName + ": " + msg;

                        var Refocus = document.activeElement.id == "InputChat";
                        var ShouldScrollDown = ElementIsScrolledToEnd("TextAreaChatLog");
                        if (document.getElementById("TextAreaChatLog") != null) {
                            document.getElementById("TextAreaChatLog").appendChild(div);
                            if (ShouldScrollDown) ElementScrollToEnd("TextAreaChatLog");
                            if (Refocus) ElementFocus("InputChat");
                        }
                    }
                }	else {
                    // Throw an error message
                    ChatRoomMessage({ Content: "ChatRoomBlockGaggedOOC", Type: "Action", Sender: Player.MemberNumber });
                }
                // Clears the chat text message
                ElementValue("InputChat", "");

            }

        }

        //---------------------------------------------------------------------------------------------------------------------------------------------
        console.log("k done~~")
    }

    //injecting the code in a <script> element into the website DOM
    var script = document.createElement("script");
    script.appendChild(document.createTextNode('('+ main +')();'));
    document.body.appendChild(script);

})();
