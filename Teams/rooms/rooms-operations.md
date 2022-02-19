---
title: Salas do Microsoft Teams e operações
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Saiba mais sobre como gerenciar Salas do Microsoft Teams.
ms.openlocfilehash: 864438890bbaef87842f6cb4b77328906036ea56
ms.sourcegitcommit: 060ba9910b8d74cbf7097cd3b8e2834afdb3db95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2022
ms.locfileid: "62909013"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Salas do Microsoft Teams e operações
 
 
Salas do Microsoft Teams é a solução de conferência da Microsoft projetada para transformar sua sala de reunião em uma experiência rica e colaborativa. Os usuários aproveitarão sua interface Microsoft Teams ou Skype for Business e os administradores de IT apreciarão um aplicativo de Windows 10 Salas do Teams de fácil implantação. Salas do Microsoft Teams é projetado para aproveitar equipamentos existentes para facilitar a instalação para Microsoft Teams ou Skype for Business sua sala de reunião.
    
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Coletando logs em Salas do Microsoft Teams
<a name="Logs"> </a>

Para coletar logs no Teams de administração, acesse Teams **dispositivos > Salas do Teams no Windows**. Selecione o nome de exibição do dispositivo para o que você deseja logs. No painel superior, selecione "Baixar logs de dispositivo". Depois de confirmar, os logs estarão prontos para download na guia Histórico após alguns minutos.

Você também pode usar o PowerShell para coletar logs. Você deve invocar o script do conjunto de log que acompanha o Salas do Microsoft Teams app. No [modo Administrador](rooms-operations.md), inicie um prompt de comando com privilégios elevados e em seguida, em seguida, o seguinte comando:
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

Os logs serão exibidos como um arquivo ZIP em c:\rigel.
  
## <a name="front-of-room-display-settings"></a>Configurações da tela frontal da sala
<a name="Display"> </a>

Configure as configurações de suas exibições de Front of Room para dar suporte ao CEC (Consumer Electronics Control) ou habilitar o modo de computador.
  
Se você desejar que uma tela frontal da sala alterna automaticamente para Salas do Teams quando ela acordar do modo de espera, determinadas condições devem ser atendidas. Esse recurso é opcional, mas tem suporte Salas do Microsoft Teams software, desde que o hardware subjacente suporte o recurso. Uma TV de consumidor usada como tela frontal de sala precisa dar suporte ao recurso CeC (Controle eletrônico de consumidor) do HDMI.  Dependendo do dock ou console selecionado (que pode não dar suporte ao CEC, consulte a documentação de suporte do fabricante), um controlador como [um HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) de Crestron ou [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) de Extron pode ser necessário para habilitar o comportamento desejado.

### <a name="change-scale-and-resolution"></a>Alterar escala e resolução

Se o tamanho da fonte em sua exibição de Frente de Sala for muito grande ou pequeno, você precisará ajustar a resolução da tela. 

1. Alternar para [o modo de administração](#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)

2. Selecione o ícone iniciar. Em **seguida, Configurações > Sistema > Display**

3. Vá para **Dimensionar e layout** e, em seguida, Alterar o tamanho de **texto, aplicativos** e outros itens e definir o dimensionamento como 100%.

4. De definir a resolução de exibição como 1080p. Se você tiver monitores duplos, de definir a escala e a resolução para ambas as telas.

5. Em seguida, selecione o ícone de início e insira **Prompt de comando**. Selecione **Executar como administrador**.

6. Execute o seguinte comando:

```cmdlet
 Powershell -ExecutionPolicy Unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentDisplayScaling.ps1 
```
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Salas do Microsoft Teams Redefinição (Restauração de Fábrica)
<a name="Reset"> </a>

Se Salas do Microsoft Teams não estiver funcionando bem, executar uma redefinição de fábrica pode ajudar. Para fazer isso, use a ferramenta Microsoft Teams de recuperação [de sala](recovery-tool.md) e siga as instruções de restauração de fábrica.

> [!NOTE]
> Há um problema conhecido em que o Salas do Microsoft Teams pode se tornar inutilizável se a opção Manter meus arquivos **- Remove Aplicativos** e configurações, mas mantém sua opção de arquivos pessoais selecionada durante o processo Windows Redefinição. Não *use* essa opção.
  
## <a name="supported-remote-options"></a>Opções remotas com suporte
<a name="RemoteOptions"> </a>

A tabela a seguir resume as operações remotas possíveis e os métodos que você pode usar para executá-las.
  

|Grupo de trabalho |Não ingresso em domínio|Ingresso em domínio|
|:-----|:-----|:-----|
|Reiniciar  <br/> |Teams de administração  <br/> Área de trabalho remota  <br/> PowerShell remoto  <br/> | <br/>Área de trabalho remota (requer mais configuração)  <br/> PowerShell remoto (requer mais configuração)  <br/> Configuration Manager  <br/> |
|Atualização do sistema operacional  <br/> |Se forem necessárias regras mais restritivas, veja as seguintes URLs de lista de permissões:  <br/> |Windows Update  <br/> WSUS  <br/> |
|Atualização de aplicativos  <br/> |Windows Store  <br/> |Windows Store  <br/> Configuration Manager  <br/> |
|Config de conta  <br/> |Teams de administração  <br/> |Teams de administração  <br/> |
|Acesso aos logs  <br/> |Teams de administração  <br/> PowerShell  <br/> |Teams de administração <br/> PowerShell  <br/>  |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Configurando a Política de Grupo para Salas do Microsoft Teams
<a name="GroupPolicy"> </a>

Esta seção aborda as configurações do sistema que Salas do Microsoft Teams depende para funcionar corretamente. 

A junção Salas do Teams a um domínio do Active Directory oferece os seguintes benefícios:

- A junção de domínio Salas do Teams permite conceder direitos administrativos a usuários e grupos de domínio. Ao fazer isso, você não precisará ter que se lembrar da senha da conta do administrador no nível da máquina local.

- Você pode implantar uma Windows de Qualidade de Serviço para Salas do Teams.

- Se usar Skype for Business, a junção de domínio ao Salas do Teams automatiza a importação da cadeia de certificados raiz privada da sua organização.

Ao ingressar no Salas do Teams a um domínio, é necessário criar uma Unidade Organizacional (UO) separada, para que você possa fornecer exclusões de OBJETO de Política de Grupo (GPO) à OU onde todos os objetos Salas do Teams residem. Desabilite toda a herança de GPO para que as configurações da Política de Grupo sem suporte não se apliquem a Salas do Teams. Crie objetos de máquina na UO antes de Salas do Teams ao domínio para garantir que as Políticas de Grupo aplicadas à UO de computadores padrão não sejam aplicadas.

> [!NOTE]
> Mesmo que você crie uma UO separada e bloqueie a herança, existem algumas políticas de grupo que podem causar problemas se elas não têm nenhum conjunto de substituição. Um conjunto de Política de Grupo sem Substituição supera uma OU com Conjunto de Herança de Política de Bloqueio.

Muitas organizações têm os seguintes GPOs, que afetam Salas do Teams funcionalidade. Verifique se você substitui ou bloqueia a herança destes:

  - Tempo limite de sessões de logon (bloqueio automático)
  - Políticas relacionadas ao gerenciamento de energia
  - Requerendo etapas adicionais de autenticação
  - Negando acesso a unidades locais
  - Avisando usuários para conexões de rede lentas
  - Iniciar um determinado programa no logon
  - Crie uma outra conta de usuário de domínio em todas as máquinas que ingressaram no domínio.
  - Push Windows Update to Salas do Teams

Ao ingressar Salas do Microsoft Teams a um domínio, verifique se as políticas de grupo não substituem as configurações na tabela a seguir.

|Configuração|Permite|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Permite Salas do Microsoft Teams inicializar  <br/> |
|Gerenciamento de Energia -\> Em AC, desligue a tela após 10 minutos  <br/> Gerenciamento de Energia -\> Em AC, nunca coloque o sistema para dormir  <br/> |Permite Salas do Microsoft Teams desativar as exibições anexadas e acordar automaticamente  <br/> |
|net accounts /maxpwage:unlimited  <br/> Ou um modo equivalente de desabilitar a expiração da senha na conta local. A impossibilidade de fazer isso pode causar uma falha no logon com a conta do Skype com uma mensagem de senha expirada. Observe que isso afeta todas as contas locais do computador. Portanto, se isso não for definido, com o tempo, a conta de administrador também vai expirar.   <br/> |Permite que a conta do Skype esteja sempre conectada  <br/> |

> [!NOTE]
> Quando Salas do Microsoft Teams é compatível com a próxima versão do sistema operacional Windows 10, Salas do Teams atualiza automaticamente para a próxima versão por meio do Windows Update. Salas do Microsoft Teams não deve ser atualizado para a próxima versão do Windows 10 manualmente ou por meio da habilitação de políticas de grupo do Windows Update for Business (WUFB) "Selecione o nível de preparação do Windows para as atualizações que você deseja receber" e "Selecione quando as versões de visualização e atualizações de recursos são recebidas" por meio do GPO. Salas do Teams com essas políticas de grupo habilitadas é conhecido por ter problemas com Windows 10 do sistema operacional.

## <a name="remote-management-using-powershell"></a>Gerenciamento remoto usando o PowerShell
<a name="RemotePS"> </a>

Você pode executar as seguintes operações de gerenciamento remotamente usando o PowerShell (consulte a tabela abaixo para exemplos de script):
  
- Obter dispositivos conectados
- Obter o status do aplicativo
- Obter informações do sistema
- Reiniciar o sistema
- Recuperar logs
- Transferir arquivos (requer uma Salas do Microsoft Teams)
    
> [!NOTE]
> Essa funcionalidade está desativada por padrão. Você precisa habilitar o PowerShell remoto para seu ambiente no Salas do Microsoft Teams para executar as operações abaixo. Consulte a documentação **[em Enable-PSRemoting](/powershell/module/microsoft.powershell.core/enable-psremoting)** para obter informações sobre como habilitar o PowerShell remoto.
  
Por exemplo, você pode habilitar o PowerShell Remoto da seguinte maneira:
  
1. Entre como Administrador em um dispositivo Salas do Microsoft Teams.
2. Abra um prompt de comando do PowerShell com elevação.
3. Insira o seguinte comando: `Enable-PSRemoting -SkipNetworkProfileCheck -Force`
4. Abra a Política de Segurança Local e adicione o grupo de segurança *Administradores* a **Segurança Configurações** >  **Local PoliciesUser** >  **Rights** **AssignmentAccess** >  este computador da rede.

Para executar uma operação de gerenciamento:
  
1. Entre em um computador com credenciais de conta que tenham permissão para executar comandos do PowerShell em um Salas do Microsoft Teams dispositivo.
2. Abra um prompt de comando normal do PowerShell no computador.
3. Copie o texto do comando da tabela abaixo e o colar no prompt.
4. Substitua  `<Device fqdn>` campos por valores FQDN apropriados ao seu ambiente.
5. Substitua  *\<path\>*  pelo nome do arquivo e o caminho local do arquivo de configuração SkypeSettings.xml mestre (ou imagem theme).
    
Para obter dispositivos anexados
  
```PowerShell
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

Obter o status de aplicativos
  
```PowerShell
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

Obter informações do sistema
  
```PowerShell
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

Reiniciar o sistema
  
```PowerShell
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

Recuperar logs
  
```PowerShell
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

Empurrar um arquivo de configuração XML (ou gráfico de tema)
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>Atualizações de software
<a name="SWupdate"> </a>

Por padrão, Salas do Microsoft Teams tenta se conectar à Windows Store para obter a versão mais recente do software Salas do Microsoft Teams software. Portanto, Salas do Teams requer acesso regular à Internet. Antes de entrar em contato com a Microsoft com problemas de suporte, certifique-se Salas do Microsoft Teams está carregado com a versão mais recente do aplicativo.
  
Salas do Microsoft Teams se conecta ao Windows Update para recuperar atualizações de firmware de dispositivos periféricos e do sistema operacional. Ele também se conecta ao Microsoft Store para recuperar atualizações de aplicativos.

Se você precisar gerenciar as atualizações de aplicativo manualmente, mas não puder seguir o procedimento normal [](https://businessstore.microsoft.com/store) para Microsoft Store para Empresas distribuir aplicativos [offline](/microsoft-store/distribute-offline-apps), você poderá adquirir pacotes de atualização Salas do Teams para executar atualizações de aplicativos em sistemas operacionais com suporte. A versão de atualização pode ficar para trás do lançamento da loja e nem sempre pode corresponder à versão mais recente disponível. Consulte [Atualizar manualmente um Salas do Microsoft Teams para](manual-update.md) saber mais.

## <a name="admin-mode-and-device-management"></a>Modo de administração e gerenciamento de dispositivo
<a name="AdminMode"> </a>

Algumas funções de gerenciamento, como a instalação manual de um certificado de AC particular, exigem Salas do Teams no modo Admin. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>Alternar para o modo Administrador e voltar quando o aplicativo Salas do Microsoft Teams está sendo executado

1. Desligue todas as chamadas em andamento e retorne para a tela inicial.
2. Selecione o ícone Engrenagem e traga o menu (as opções **são Configurações**, **Acessibilidade** e **Reiniciar Dispositivo** ).
3. Selecione **Configurações**.
4. Insira a senha do Administrador. A tela Configuração será exibida.  Se o dispositivo não for ingressado no domínio, a conta administrativa local (nome de usuário "Administrador") será usada por padrão. A senha padrão para essa conta é 'sfb'. Altere essa senha assim que possível. Se o computador for ingressado em domínio, você poderá entrar com uma conta de domínio privilegiada apropriadamente.
5. Selecione **Windows Configurações** na coluna esquerda.
6. Faça logon no desktop usando as credenciais administrativas. Você terá os privilégios necessários para gerenciar o dispositivo.
7. Execute as tarefas administrativas necessárias.
8.  Reinicie o computador quando terminar.
    
O console retorna ao seu modo de operação normal. O procedimento a seguir exige que você conecte um teclado ao dispositivo, caso ele esteja sem.  
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>Alternar para o Modo de Administração e voltar quando o aplicativo Salas do Microsoft Teams falha

1. Pressione a tecla do Windows cinco vezes em uma sucessão rápida. Isso levará você para a tela de logon do Windows.  
2. Faça logon no desktop usando as credenciais administrativas.
3. Execute as tarefas administrativas necessárias.
4. Reinicie o computador quando terminar.

    > [!NOTE]
    > Esse método não registra o usuário Skype ou termina o aplicativo normalmente, mas você o usaria se o aplicativo não estivesse respondendo e o outro método não estivesse disponível. 

   O console é reiniciado em seu modo de operação normal, executando o Salas do Microsoft Teams app. Você pode remover o teclado, se anexar um para concluir este procedimento.
   ## <a name="troubleshooting-tips"></a>Dicas para solução de problemas
   <a name="TS"> </a>

- Os convites de reunião podem não aparecer quando enviados através dos limites de domínio (por exemplo, entre duas empresas). Nesses casos, os administradores de IT devem decidir se permitem que usuários externos agendem uma reunião. Consulte o artigo para o cmdlet Exchange PowerShell [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing), especificamente o parâmetro 'ProcessExternalMeetingMessages'.
- Salas do Microsoft Teams não dá suporte Exchange redirecionamentos de Descoberta Automática via Exchange 2010.
- Em geral, é uma boa prática para os administradores de IT desabilitar os pontos de extremidade de áudio que eles não pretendem usar.
- No caso de uma imagem de espelho ser exibida na visualização da sala, o administrador de IT poderá corrigir com a energia da câmera de ciclo ou invertendo a orientação da imagem usando as configurações da câmera.
- Sabe-se que pode ocorrer a perda do acesso à tela touch do console. Nesses casos, o problema às vezes é resolvido reiniciando Salas do Teams.
- Sabe-se que pode ocorrer a perda do áudio local ao conectar um computador ao console via entrada com fio. Nesses casos, reiniciar o computador pode resolver o problema de reprodução do áudio local.
