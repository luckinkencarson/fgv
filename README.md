
--[[
--------------- [ SHHHH V3.0 BETA ] ---------------

[ Mouse Keys ] : Left Click = Enum.UserInputType.MouseButton1, Right Click = Enum.UserInputType.MouseButton2, Scroll Wheel Click = Enum.UserInputType.MouseButton3

[ Keyboard Keys ] : https://learn.microsoft.com/en-us/dotnet/api/system.windows.forms.keys?view=windowsdesktop-8.0

[ Bodyparts ] : https://create.roblox.com/docs/reference/engine/enums/BodyPartR15

[ EasingStyles ] : https://create.roblox.com/docs/reference/engine/enums/EasingStyle


--------------- {!! READ !!} ---------------

Silent Aim :

Lock = Silent Aim, Target

( Setting ['Target Mode'] to 'Auto' Turns it into a silent Aim like 'Auto' get target )
( Setting ['Target Mode'] to 'Key' Turns it into a Target Lock like 'Key' toggle get target )

hood customs? turn anti aim viewer off
want to use spam guns? turn anti aim viewer off

--------------- { devlog } ---------------

inventory sorter
chat cmds
misc
auto360 ( customizable now uca nmake it 180 )
closegame
fakespike ( even godlier now )
autoreset ( better )
settings
low gfx ( wont make ur head glassy anymore )
muteboombox
trashtalk
option : cam wallcheck if already targeted and target goes behind wall unlock 
MACRO : custom zoom amount
hc full bypass thanks to osi

add :
triggerbot
mem spoofer

--]]



getgenv().Shhhh = {

    ['Loader'] = {['Key'] = 'KeyHere', ['Fps Cap'] = 240; ['Intro'] = false; ['Warnings'] = true};

    ['Panic'] = {
        ['Enabled'] = true;
        ['Key'] = 'P';
        ['Notification'] = false;
        ['Turn Lock Off'] = false; --[ Turns Lock off ]
        ['Turn CamLock Off'] = false; --[ Turns Camlock off ]
        ['Turn Visuals Off'] = true; --[ Turns visuals off like crosshair, fov,notifications ]
        ['Turn Notifications Off'] = true;
    };

    ['Silent Aim'] = {
        ['Enabled'] = true;                 --[ Go down to Custom Auto Pred Section ]
        ['Prediction'] = {['Amount'] = 0.135; ['Custom Auto Prediction'] = true};
        ['HitChance'] = {['Enabled'] = true; ['Amount'] = 100};
        ['Toggle'] = {
            ['Target Mode'] = 'Auto'; --[ Key = ( Toggle Mode ) , Auto = ( Silent Aim Mode auto get target ) ]
            ['Hold'] = false;
            ['Mode'] = 'Key'; --['Key', 'Mouse']
            ['Key'] = 'T';
            ['Mouse'] = Enum.UserInputType.MouseButton2;
        };
        ['HitPart'] = {
            ['Part'] = 'HumanoidRootPart';
            ['ClosestMode'] = true;
            ['Mode'] = 'Nearest Point'; -- 'Nearest Point', 'Nearest Part'
        };
        ['Notification'] = {
            ['Enabled'] = false;
            ['Delay'] = 1.5; --[ seconds ]
            ['Color'] = Color3.fromRGB(152, 194, 219);
            ['Logo Text'] = 'Shhhh V.3';
        };
        ['Checks'] = {
            ['WallCheck'] = true;
            ['Knocked'] = true;
            ['Crew Check'] = true;
            ['Anti Curve'] = true;
            ['Anti Ground Shots'] = {
                ['Enabled'] = true;
                ['Jump'] = 0;
                ['Fall'] = 0.4
            }
        };
    };

    ['CamLock'] = {
        ['Enabled'] = true;
        ['Mode'] = 'Camera'; --[ Mouse = Mouse follows target, Camera = Camera follows target ]
        ['Prediction'] = 0.135;
        ['Smoothness'] = 0.03;
        ['Toggle'] = {
            ['Target Mode'] = 'Key'; --[ Key = ( Toggle Mode ) , Auto = (Silent Aim Mode auto get target ) ]
            ['Hold'] = false;
            ['Mode'] = 'Key'; --['Key', 'Mouse']
            ['Key'] = 'Q';
            ['Mouse'] = Enum.UserInputType.MouseButton2;
        };
        ['HitPart'] = {
            ['Part'] = 'Head';
            ['ClosestMode'] = true;
            ['Mode'] = 'Nearest Part'; -- 'Nearest Point', 'Nearest Part'
        };
        ['Notification'] = {
            ['Enabled'] = false;
            ['Delay'] = 1.5; --[ seconds ]
            ['Color'] = Color3.fromRGB(152, 194, 219);
            ['Logo Text'] = 'Shhhh V.3';
        };
        ['Shake'] = {
            ['Enabled'] = false;
            ['Randomized'] = false;
            ['Settings'] = {['X'] = 15; ['Y'] = 15; ['Z'] = 15};
            ['Max Randomized Values'] = {['X'] = 40; ['Y'] = 40; ['Z'] = 40}; --[ Max Amount you want it to randomized between 0-number ]
        };
        ['Checks'] = {
            ['WallCheck'] = {['Enabled'] = true; ['UnlockWhenTargetGoesBehindWall'] = true};
            ['Knocked'] = true;
            ['Holding Gun'] = true; --[ only on when holding a gun ]
            ['Crew Check'] = true;
        };
        ['EasingStyle'] = {['First'] = 'InOut'; ['Second'] = 'Out'};
    };

    ['Fov'] = {

        ['Outlines'] = false; --[ will make u drop around 10 fps turn on if you want ]

        ['Silent Aim'] = {
            ['Settings'] = {
                ['Stick'] = false;
                ['Stick Part'] = 'HumanoidRootPart';
                ['Fov Panic'] = false; --[ Turns Visible Fov on and off ]
                ['Fov Panic Key'] = 'L';
            };

            ['Visuals'] = {
                ['Visible'] = true;
                ['Size'] = 14;
                ['Filled'] = true;
                ['OutLine Filled'] = false;
                ['OutLine Thickness'] = 1; --[ set to 4 if transparency = 1 ]
                ['OutLine Transparency'] = 1;
                ['Color'] = Color3.fromRGB(152, 194, 219);
                ['Transparency'] = 0.1;
            };
        };

        ['Aim Assist'] = {
            ['Settings'] = {
                ['Stick'] = false;
                ['Stick Part'] = 'HumanoidRootPart';
                ['Fov Panic'] = false; --[ Turns Visible Fov on and off ]
                ['Fov Panic Key'] = 'L';
            };

            ['Visuals'] = {
                ['Visible'] = true;
                ['Size'] = 90;
                ['Filled'] = false;
                ['OutLine Filled'] = false;
                ['OutLine Thickness'] = 4; -- [ set to 4 if transparency = 1 ]
                ['OutLine Transparency'] = 1;
                ['Color'] = Color3.fromRGB(152, 194, 219);
                ['Transparency'] = 1;
            };
        };
    };
    ['Resolver'] = {
        ['Enabled'] = true;
        ['Check Method'] = 'Position'; --{ 'Position', 'CFrame, 'Velocity' }    [ DEFAULT IS GOOD ALREADY CHANGE IF NEEDED ]
        ['Method']  = 'RecalculateVelocity'; --{ 'BuiltVelocity', 'RecalculateVelocity', 'Move Direction', 'AttenuateVelocity' }    [ DEFAULT IS GOOD ALREADY CHANGE IF NEEDED ]
        ['Strength'] = 'Very Strong'; --{ leave as default }
    };
    ['Stuff'] = {
        ['Anti Aim Viewer'] = true; --{ makes spam guns not work like AK,LMG, SMG Etc.. }
        ['Respawn Same Position'] = true; --{ makes you respawn where you die }
    };
    ['Inventory Sorter'] =  {
        ['Enabled'] = false;
        ['Sort Food'] = false;
        ['Keybind'] = 'X';
        ['Slot 1']  = '[Revolver]';
        ['Slot 2']  = '[Double-Barrel SG]';
        ['Slot 3']  = '[TacticalShotgun]';
        ['Slot 4']  = '[Shotgun]';
        ['Slot 5']  = '[Knife]';
        ['Slot 6']  = '[Katana]';
    };
    ['Macro'] = {
        ['Enabled'] = true;
        ['Hold'] = false;
        ['KeyBind'] = 'X';
        ['Mode'] = 'First Person';
        ['Zoom Amounts'] = {['First Person'] = 0.6; ['Third Person'] = 5};
        ['Notification'] = {
            ['Enabled'] = false;
            ['Delay'] = 1.5; --[ seconds ]
            ['Color'] = Color3.fromRGB(152, 194, 219);
            ['Logo Text'] = 'Shhhh V.3';
        };
    };
    ['Chat Commands'] = {

        --{ Usage : $fov 20 changes fov to 20 }--
        --{ change them to whatever you like }--
    
        ['Enabled'] = false;
        ['Notification'] = true;
        ['Silent Fov'] = '$sfov';
        ['CamLock Fov'] = '$cfov';
        ['Silent Pred'] = '$spred';
        ['CamLock Pred'] = '$cpred';
        ['CamLock Smoothness'] = '$csmooth';
        ['HitChance'] = '$hc';
        ['Auto Prediction'] = '$autop'; --[$sfov treue or false ]
    };
    ['Misc'] = {
        ['Auto360'] = {
            ['Enabled'] = false;
            ['SpinKeybind'] = 'Q';
            ['SpinSpeed'] = 4;
            ['Roation Amount'] = 360; -- [ you can also change to 180 ofc ]
        };
        ['CloseGame'] = {
            ['Enabled'] = false;
            ['KeyBind'] = 'M';
            ['UseDelay'] = false;
            ['Delay'] = 1;
        };
        ['FakeSpike'] = {
            ['Enabled'] = false;
            ['FakeSpikeKeybind'] = 'K';
            ['SpikeDuration'] = 1;
        };
        ['AutoReset'] = {
            ['Enabled'] = false;
            ['AutoResetKeybind'] = 'L';
            ['UseDelay'] = false;
            ['Delay'] = 0.1;
        };
        ['Settings'] = {
            ['AutoLowGFX'] = true; --[ Boosts FPS and Smoother game ]
            ['MuteBoomBox'] = true;
        };
        ['TrashTalk'] = {
            ['Enabled'] = false;
            ['KeyBind'] = "T"; -- [ whenever you click this keybind it spams the messages randomly ]
            ['Method'] = "2"; -- [ 1 = ( random message from the table ) 2 = ( all messages in a row ) ]
            ['Delay'] = 0.3; -- [ for method 2 ( 0.3 miliseconds currently ) ]
                ['Messages'] = { -- [ put messages in the Sections below ]
                    'message1';
                    'message2';
                    'message3';
                    'message4';
                    'message5';
                    'message6';
                };
        };
    };
    ['Visuals'] = {
        ['HighLight'] = {
            ['Enabled'] = true;
            ['Fill Color'] = Color3.fromRGB(152, 194, 219);
            ['Outline Color'] = Color3.fromRGB(152, 194, 219);
        };
    };
    ['Crosshair'] = {
        ['Enabled'] = true;
        ['Stick'] = false; -- [ Sticks to target]
        ['Stick Part'] = 'HumanoidRootPart';
        ['Color'] = Color3.fromRGB(152, 194, 219);
        ['Spin'] = true;
        ['Length'] = 35;
        ['Width'] = 1.5;
        ['Radius'] = 25;
        ['Resize'] = true;
        ['SpinSpeed'] = 200;
        ['ResizeSpeed'] = 150;
        ['ResizeMax'] = 35;
        ['EasingStyle'] = 'InOut';
        ['SpinEasingStyle'] = 'Circular';
    };
    ['Custom Auto Prediction Preds'] = {
        ['Range Settings'] = {
            ['Close'] = true; ['Mid'] = true; ['Far'] = true;
            ['Close Range'] = 15; ['Mid Range'] = 40; ['Far Range'] = 9e9;

            ['Debug'] = false; --[ prints the prediction in f9 ]
        };

        --{ turn the ranges off if you don't want them }--

        ['20']  = {['Normal'] = 0.12547; ['Close'] = 0.1057; ['Mid'] = 0.1259; ['Far'] = 0.11327};
        ['30']  = {['Normal'] = 0.124821; ['Close'] = 0.10554; ['Mid'] = 0.12417; ['Far'] = 0.11504};
        ['40']  = {['Normal'] = 0.1259910; ['Close'] = 0.1059910 ; ['Mid'] = 0.1259910 ; ['Far'] = 0.1159910 };
        ['50']  = {['Normal'] = 0.12681; ['Close'] = 0.10731; ['Mid'] = 0.12731; ['Far'] = 0.11731};
        ['60']  = {['Normal'] = 0.12241; ['Close'] = 0.10841; ['Mid'] = 0.13481; ['Far'] = 0.12647};
        ['70']  = {['Normal'] = 0.12861; ['Close'] = 0.10419; ['Mid'] = 0.13237; ['Far'] = 0.12567724521};
        ['80']  = {['Normal'] = 0.12941; ['Close'] = 0.10189; ['Mid'] = 0.13481; ['Far'] = 0.12};
        ['90']  = {['Normal'] = 0.13587; ['Close'] = 0.11181; ['Mid'] = 0.13781; ['Far'] = 0.125451};
        ['100'] = {['Normal'] = 0.138; ['Close'] = 0.138; ['Mid'] = 0.1246; ['Far'] = 0.141};
        ['110'] = {['Normal'] = 0.14781; ['Close'] = 0.134487; ['Mid'] = 0.147475; ['Far'] = 0.13467};
        ['120'] = {['Normal'] = 0.148767; ['Close'] = 0.1385; ['Mid'] = 0.14457; ['Far'] = 0.1348564};
        ['130'] = {['Normal'] = 0.141517; ['Close'] = 0.13187; ['Mid'] = 0.143561; ['Far'] = 0.138448};
        ['140'] = {['Normal'] = 0.1534; ['Close'] = 0.1452; ['Mid'] = 0.15348; ['Far'] = 0.14454};
        ['150'] = {['Normal'] = 0.152580; ['Close'] = 0.14626; ['Mid'] = 0.154677; ['Far'] = 0.14954};
        ['160'] = {['Normal'] = 0.16145; ['Close'] = 0.15215; ['Mid'] = 0.16485; ['Far'] = 0.14515};
        ['170'] = {['Normal'] = 0.164714; ['Close'] = 0.15725; ['Mid'] = 0.16755; ['Far'] = 0.149285};
        ['180'] = {['Normal'] = 0.17145; ['Close'] = 0.162875; ['Mid'] = 0.17245; ['Far'] = 0.152520};
        ['190'] = {['Normal'] = 0.173455; ['Close'] = 0.165145; ['Mid'] = 0.17254; ['Far'] = 0.154255};
        ['200'] = {['Normal'] = 0.18245; ['Close'] = 0.17815; ['Mid'] = 0.18150; ['Far'] = 0.16845}; 
    };
    ['GunFov'] = {
        ['Enabled'] = false;
        ['Ranges'] = false;
        ['Debug'] = false; --[ Prints Current Range, HitChance, Fov ]--
        ['Settings'] = {['Fov'] = true; ['HitChance'] = true};
        ['Ranges Distances'] = {['Close Range'] = 15; ['Mid Range'] = 40; ['Far Range'] = 9e9};
        ['Guns'] = {

            --{ Default Section triggers when Range is off or no one is being targeted }--

            ['DoubleBarrel'] = {
                ['Default'] = {['Fov'] = 25; ['HitChance'] = 100};

                ['Close'] = {['Fov'] = 16; ['HitChance'] = 100};
                ['Mid']   = {['Fov'] = 12; ['HitChance'] = 100};
                ['Far']   = {['Fov'] = 7;  ['HitChance'] = 100};
            };
            ['Revolver'] = {
                ['Default'] = {['Fov'] = 25; ['HitChance'] = 100};

                ['Close'] = {['Fov'] = 16; ['HitChance'] = 100};
                ['Mid']   = {['Fov'] = 12; ['HitChance'] = 100};
                ['Far']   = {['Fov'] = 17; ['HitChance'] = 100};
            };
            ['TacticalShotgun'] = {
                ['Default'] = {['Fov'] = 25; ['HitChance'] = 100};

                ['Close'] = {['Fov'] = 16; ['HitChance'] = 100};
                ['Mid']   = {['Fov'] = 12; ['HitChance'] = 100};
                ['Far']   = {['Fov'] = 17; ['HitChance'] = 100};
            };
            ['Drum-Shotgun'] = {
                ['Default'] = {['Fov'] = 25; ['HitChance'] = 100};

                ['Close'] = {['Fov'] = 16; ['HitChance'] = 100};
                ['Mid']   = {['Fov'] = 12; ['HitChance'] = 100};
                ['Far']   = {['Fov'] = 7;  ['HitChance'] = 100};
            };
            ['DrumGun'] = {
                ['Default'] = {['Fov'] = 25; ['HitChance'] = 100};

                ['Close'] = {['Fov'] = 16; ['HitChance'] = 100};
                ['Mid']   = {['Fov'] = 12; ['HitChance'] = 100};
                ['Far']   = {['Fov'] = 7;  ['HitChance'] = 100};
            };
            ['Rifle'] = {
                ['Default'] = {['Fov'] = 25; ['HitChance'] = 100};

                ['Close'] = {['Fov'] = 16; ['HitChance'] = 100};
                ['Mid']   = {['Fov'] = 12; ['HitChance'] = 100};
                ['Far']   = {['Fov'] = 7;  ['HitChance'] = 100};
            };
            ['SMG'] = {
                ['Default'] = {['Fov'] = 25; ['HitChance'] = 100};

                ['Close'] = {['Fov'] = 16; ['HitChance'] = 100};
                ['Mid']   = {['Fov'] = 12; ['HitChance'] = 100};
                ['Far']   = {['Fov'] = 7;  ['HitChance'] = 100};
            };
            ['Shotgun'] = {
                ['Default'] = {['Fov'] = 25; ['HitChance'] = 100};

                ['Close'] = {['Fov'] = 16; ['HitChance'] = 100};
                ['Mid']   = {['Fov'] = 12; ['HitChance'] = 100};
                ['Far']   = {['Fov'] = 7;  ['HitChance'] = 100};
            };
            ['SilencerAR'] = {
                ['Default'] = {['Fov'] = 25; ['HitChance'] = 100};

                ['Close'] = {['Fov'] = 16; ['HitChance'] = 100};
                ['Mid']   = {['Fov'] = 12; ['HitChance'] = 100};
                ['Far']   = {['Fov'] = 7;  ['HitChance'] = 100};
            };
            ['Silencer'] = {
                ['Default'] = {['Fov'] = 25; ['HitChance'] = 100};

                ['Close'] = {['Fov'] = 16; ['HitChance'] = 100};
                ['Mid']   = {['Fov'] = 12; ['HitChance'] = 100};
                ['Far']   = {['Fov'] = 7;  ['HitChance'] = 100};
            };
            ['P90'] = {
                ['Default'] = {['Fov'] = 25; ['HitChance'] = 100};

                ['Close'] = {['Fov'] = 16; ['HitChance'] = 100};
                ['Mid']   = {['Fov'] = 12; ['HitChance'] = 100};
                ['Far']   = {['Fov'] = 7;  ['HitChance'] = 100};
            };
            ['AK47'] = {
                ['Default'] = {['Fov'] = 25; ['HitChance'] = 100};

                ['Close'] = {['Fov'] = 16; ['HitChance'] = 100};
                ['Mid']   = {['Fov'] = 12; ['HitChance'] = 100};
                ['Far']   = {['Fov'] = 7;  ['HitChance'] = 100};
            };
            ['AR'] = {
                ['Default'] = {['Fov'] = 25; ['HitChance'] = 100};

                ['Close'] = {['Fov'] = 16; ['HitChance'] = 100};
                ['Mid']   = {['Fov'] = 12; ['HitChance'] = 100};
                ['Far']   = {['Fov'] = 7;  ['HitChance'] = 100};
            };
            ['AUG'] = {
                ['Default'] = {['Fov'] = 25; ['HitChance'] = 100};

                ['Close'] = {['Fov'] = 16; ['HitChance'] = 100};
                ['Mid']   = {['Fov'] = 12; ['HitChance'] = 100};
                ['Far']   = {['Fov'] = 7;  ['HitChance'] = 100};
            };
            ['Glock'] = {
                ['Default'] = {['Fov'] = 25; ['HitChance'] = 100};

                ['Close'] = {['Fov'] = 16; ['HitChance'] = 100};
                ['Mid']   = {['Fov'] = 12; ['HitChance'] = 100};
                ['Far']   = {['Fov'] = 7;  ['HitChance'] = 100};
            };
        };
    };
};

loadstring(game:HttpGet('https://raw.githubusercontent.com/farzadxx/ratz/main/shhhh', true))()
