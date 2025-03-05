local Fluent = loadstring(game:HttpGet("https://github.com/dawid-scripts/Fluent/releases/latest/download/main.lua"))()

-- Definir a cor vermelha para personalização
local redColor = Color3.fromRGB(255, 0, 0)  -- Cor vermelha

-- Função para traduzir a interface
local function translateInterface(language)
    local translations = {
        ["pt"] = {
            Title = "Vitor Hub : Scripts Hub",
            SubTitle = "por Ki Night",
            ButtonText = "Abrir/Fechar",
            KeyPrompt = "Insira a chave para continuar",
            SubmitButton = "Enviar",
            ErrorTitle = "Erro",
            ErrorText = "Chave inválida, tente novamente."
        },
        ["en"] = {
            Title = "Vitor Hub : Scripts Hub",
            SubTitle = "by Ki Night",
            ButtonText = "Open/Close",
            KeyPrompt = "Enter the key to continue",
            SubmitButton = "Submit",
            ErrorTitle = "Error",
            ErrorText = "Invalid key, try again."
        }
    }

    return translations[language] or translations["en"]
end

-- Função de validação de chave
local validKey = "123456"  -- Defina a chave de acesso aqui
local function askForKey()
    local keyWindow = Instance.new("ScreenGui")
    local frame = Instance.new("Frame")
    local title = Instance.new("TextLabel")
    local keyInput = Instance.new("TextBox")
    local submitButton = Instance.new("TextButton")

    keyWindow.Name = "KeyWindow"
    keyWindow.Parent = game.Players.LocalPlayer.PlayerGui

    frame.Size = UDim2.new(0, 400, 0, 200)
    frame.Position = UDim2.new(0.5, -200, 0.5, -100)
    frame.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
    frame.BorderSizePixel = 0
    frame.Parent = keyWindow

    title.Text = "Insira a chave para continuar"
    title.Size = UDim2.new(1, 0, 0.2, 0)
    title.TextColor3 = Color3.fromRGB(255, 255, 255)
    title.BackgroundTransparency = 1
    title.Parent = frame

    keyInput.Size = UDim2.new(0, 300, 0, 50)
    keyInput.Position = UDim2.new(0.5, -150, 0.4, 0)
    keyInput.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    keyInput.Text = ""
    keyInput.ClearTextOnFocus = true
    keyInput.Parent = frame

    submitButton.Text = "Enviar"
    submitButton.Size = UDim2.new(0, 100, 0, 40)
    submitButton.Position = UDim2.new(0.5, -50, 0.7, 0)
    submitButton.BackgroundColor3 = Color3.fromRGB(0, 255, 0)
    submitButton.TextColor3 = Color3.fromRGB(0, 0, 0)
    submitButton.Parent = frame

    submitButton.MouseButton1Click:Connect(function()
        if keyInput.Text == validKey then
            keyWindow:Destroy()  -- Fecha a janela de chave
            createMainGUI()  -- Chama a função para criar a GUI principal
        else
            game:GetService("StarterGui"):SetCore("SendNotification", {
                Title = "Erro",
                Text = "Chave inválida, tente novamente.",
                Duration = 2
            })
        end
    end)
end

-- Função para criar a GUI principal
local function createMainGUI()
    -- Solicitar ao usuário a linguagem desejada
    local selectedLanguage = "pt"  -- Modifique aqui para "en" ou outro idioma
    local translation = translateInterface(selectedLanguage)

    local Window = Fluent:MakeWindow({
        Title = translation.Title,
        SubTitle = translation.SubTitle,
        SaveFolder = "VITORHUb | VITORHUBSCRIPTSHUB",
        BackgroundColor = redColor,
        TitleTextColor = Color3.fromRGB(255, 255, 255),
        ButtonColor = redColor,
        ButtonTextColor = Color3.fromRGB(255, 255, 255),
        BorderColor = Color3.fromRGB(139, 0, 0),
    })

    -- Criando as abas para os jogos
    local BloxFruits = Window:MakeTab({"Blox Fruits", "cherry"})
    local FischTab = Window:MakeTab({"Fisch", "plane"})
    local BrookHavenTab = Window:MakeTab({"Brook Haven", "house"})
    local KingLegacyTab = Window:MakeTab({"King Legacy", "crown"})
    local BlueLockRivalsTab = Window:MakeTab({"Blue Lock Rivals", "soccer"})
    local BladeBallTab = Window:MakeTab({"Blade Ball", "shield"})
    local MurderMystery2Tab = Window:MakeTab({"Murder Mystery 2", "knife"})
    local PetSimulatorTab = Window:MakeTab({"Pet Simulator X", "pawprint"})
    local CarDealershipTab = Window:MakeTab({"Car Dealership Tycoon", "car"})
    local ShipTycoonTab = Window:MakeTab({"Ship Tycoon", "ship"})
    local OtherGamesTab = Window:MakeTab({"Outros Jogos", "star"})
    local TowerDefenseTab = Window:MakeTab({"Tower Defense Simulator", "tower"})
    local ArsenalTab = Window:MakeTab({"Arsenal", "gun"})
    local BuildABoatTab = Window:MakeTab({"Build A Boat", "boat"})
    local AdoptMeTab = Window:MakeTab({"Adopt Me", "heart"})
    local JailbreakTab = Window:MakeTab({"Jailbreak", "lock"})
    local ShindoLifeTab = Window:MakeTab({"Shindo Life", "ninja"})
    local AnimeFightersTab = Window:MakeTab({"Anime Fighters", "anime"})
    local FlickerTab = Window:MakeTab({"Flicker", "flash"})
    local StrucidTab = Window:MakeTab({"Strucid", "shooting"})
    local NaturalDisastersTab = Window:MakeTab({"Natural Disasters", "earthquake"})
    local MurderMysteryXTab = Window:MakeTab({"Murder Mystery X", "knife"})
    -- Novas abas:
    local ArsenalNewTab = Window:MakeTab({"Arsenal Nova", "gun"})
    local NewGameTab = Window:MakeTab({"Novo Jogo", "star"})

    -- Exemplo de como criar uma tabela com scripts em cada categoria
    local allScripts = {
        BloxFruits = {
            {"Redz Hub", "https://raw.githubusercontent.com/realredz/BloxFruits/refs/heads/main/Source.lua"},
            {"Cokka Hub", "https://raw.githubusercontent.com/UserDevEthical/Loadstring/main/CokkaHub.lua"},
            -- Adicione mais scripts aqui até 300 ou mais...
        },

        PetSimulatorTab = {
            {"Pet Simulator X Auto Farm", "https://raw.githubusercontent.com/xyz/petsimulatorx/main/autofarm.lua"},
            {"Pet Simulator X Script", "https://raw.githubusercontent.com/user123/psx/main/script.lua"},
            -- Adicione mais scripts aqui até 300 ou mais...
        },

        ArsenalNewTab = {
            {"Arsenal New Script", "https://raw.githubusercontent.com/NewArsenalScripts/script.lua"},
            -- Adicione mais scripts aqui...
        },

        NewGameTab = {
            {"Novo Jogo Script", "https://raw.githubusercontent.com/NewGameScripts/script.lua"},
            -- Adicione mais scripts aqui...
        }
    }

    -- Função para adicionar botões de script
    local function addButtonToTab(tab, scripts)
        for _, script in ipairs(scripts) do 
            local script_name = script[1]
            local script_url = script[2]

            -- Adiciona o botão para o script
            tab:AddButton({
                Text = script_name,
                BackgroundColor = redColor,
                TextColor = Color3.fromRGB(255, 255, 255),
                function() 
                    local Dialog = Window:Dialog({
                        Title = "Confirmação",
                        Text = "Deseja executar o script " .. script_name .. "?",
                        Options = {
                            {"Sim", function() loadstring(game:HttpGet(script_url, true))() end}, 
                            {"Não", function() end}
                        }
                    })
                end
            })
        end
    end

    -- Adicionando scripts
    for category, scripts in pairs(allScripts) do
        local tab = _G[category]
        if tab then
            addButtonToTab(tab, scripts)
        end
    end

    -- Criar o botão de abrir/fechar a GUI
    local toggleButton = Instance.new("TextButton")
    toggleButton.Size = UDim2.new(0, 100, 0, 50)
    toggleButton.Position = UDim2.new(0.5, -50, 0.5, -25)
    toggleButton.BackgroundColor3 = redColor
    toggleButton.Text = translation.ButtonText
    toggleButton.TextColor3 = Color3.fromRGB(255, 255, 255)
    toggleButton.Parent = game.Players.LocalPlayer.PlayerGui:WaitForChild("ScreenGui")

    -- Variável para verificar se a GUI está visível ou não
    local guiVisible = true

    -- Função para alternar a visibilidade da GUI
    toggleButton.MouseButton1Click:Connect(function()
        if guiVisible then
            Window:Hide()  -- Esconde a GUI
        else
            Window:Show()  -- Mostra a GUI
        end
        guiVisible = not guiVisible
    end)
end

-- Iniciar a solicitação da chave
askForKey()
