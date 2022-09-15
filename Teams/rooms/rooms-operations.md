---
title: Salas do Microsoft Teams manutenção e operações
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Saiba mais sobre como gerenciar Salas do Microsoft Teams.
ms.openlocfilehash: 85979448c425f2ab0de9a5956ba4e74b2a5697cc
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706658"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Salas do Microsoft Teams manutenção e operações
 
 
Salas do Microsoft Teams é a solução de conferência da Microsoft projetada para transformar sua sala de reunião em uma experiência rica e colaborativa. Os usuários aproveitarão sua interface familiar do Microsoft Teams ou Skype for Business e os administradores de TI apreciarão um aplicativo de Windows 10 Salas do Teams gerenciado e implantado com facilidade. Salas do Microsoft Teams é projetado para aproveitar os equipamentos existentes para facilitar a instalação e trazer o Microsoft Teams ou Skype for Business para sua sala de reunião.
    
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Coletando logs no Salas do Microsoft Teams
<a name="Logs"> </a>

Para coletar logs no Centro de administração do Teams, acesse os **dispositivos do Teams > Salas do Teams no Windows**. Selecione o nome de exibição do dispositivo para o qual você deseja obter logs. No painel superior, selecione "Baixar logs do dispositivo". Depois de confirmar, os logs estarão prontos para download na guia Histórico após alguns minutos.

Você também pode usar o PowerShell para coletar logs. Você deve invocar o script de coleção de logs fornecido com o Salas do Microsoft Teams aplicativo. No [Administração,](rooms-operations.md) inicie um prompt de comando com privilégios elevados e emita o seguinte comando:
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

Os logs serão exibidos como um arquivo ZIP em c:\rigel.

### <a name="managing-disk-space"></a>Gerenciando espaço em disco
<a name="Space"> </a>

Os logs baixados no dispositivo podem assumir espaço em disco. Se os logs não forem limpos regularmente, eles poderão interferir na funcionalidade normal da sala. Salas do Teams exclui os logs baixados após 30 dias. Os administradores de TI podem substituir a limpeza de log usando a configuração do registro do dispositivo.

|Configuração|Permite|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\PPI\SkypeSettings\LogCleanupAgeThreshold  <br/> |Limpa os logs após 30 dias.  <br/> |
  
## <a name="front-of-room-display-settings"></a>Configurações de exibição da frente da sala
<a name="Display"> </a>

Defina as configurações das exibições do Front of Room para dar suporte ao CEC (Controle eletrônico do consumidor) ou habilitar o modo de computador.
  
Se você desejar que uma exibição frontal da sala alterne automaticamente para Salas do Teams quando ela acordar do modo de espera, determinadas condições deverão ser atendidas. Esse recurso é opcional, mas tem suporte Salas do Microsoft Teams software, desde que o hardware subjacente dê suporte ao recurso. Uma TV de consumidor usada como tela frontal da sala precisa dar suporte ao recurso CEC (Controle eletrônico do consumidor) do HDMI.  Dependendo do encaixe ou do console selecionado (que pode não dar suporte a CEC, consulte a documentação de suporte do fabricante), um controlador como [um HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) da Crestron ou [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) da Extron pode ser necessário para habilitar o comportamento desejado.

### <a name="scale-and-resolution"></a>Escala e resolução

Para obter Salas do Teams experiência projetada, suas telas de frente de sala precisam atender aos requisitos de resolução e escala.

Para definir a escala e a resolução de suas telas front-of-rooms remotamente, consulte Gerenciar um [Salas do Microsoft Teams de console remotamente com um arquivo de](xml-config-file.md#set-front-of-room-scale-and-resolution) configuração XML.

Para definir a escala e a resolução manualmente nas configurações Salas do Teams administrador:

1. Na sala do Teams, alterne para o [modo de administrador](#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)

2. Selecione o ícone iniciar. Em **seguida, configurações > exibição > sistema**

3. Vá para **Escala e layout**, altere o tamanho do texto **, aplicativos** e outros itens e defina o dimensionamento como 100%.

4. Defina a resolução de exibição como 1080p. Se você tiver monitores duplos, defina a escala e a resolução para ambas as telas.

5. Em seguida, selecione o ícone iniciar e insira **o prompt de comando**. Selecione **Executar como administrador**.

6. Execute o seguinte comando:

```cmdlet
 Powershell -ExecutionPolicy Unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentDisplayScaling.ps1 
```

7. Reinicie o dispositivo.
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Salas do Microsoft Teams redefinição (restauração de fábrica)
<a name="Reset"> </a>

Se Salas do Microsoft Teams estiver funcionando bem, executar uma redefinição de fábrica poderá ajudar. Para fazer isso, use a ferramenta [Salas do Microsoft Teams recuperação e](recovery-tool.md) siga as instruções de restauração de fábrica.

> [!NOTE]
> Há um problema conhecido em que o Salas do Microsoft Teams pode se tornar inutilizável se a opção Manter meus arquivos – Remove **aplicativos** e configurações, mas mantém sua opção de arquivos pessoais selecionada durante o processo de Redefinição do Windows. Não *use* essa opção.
  
## <a name="supported-remote-options"></a>Opções remotas com suporte
<a name="RemoteOptions"> </a>

A tabela a seguir resume as operações remotas possíveis e os métodos que você pode usar para executá-las.
  

|Grupo de trabalho |Não ingresso em domínio|Ingresso em domínio|
|:-----|:-----|:-----|
|Reiniciar  <br/> |Centro de administração do Teams  <br/> Área de trabalho remota  <br/> PowerShell remoto  <br/> | <br/>Área de trabalho remota (requer configuração adicional)  <br/> PowerShell remoto (requer configuração adicional)  <br/> Configuration Manager  <br/> |
|Atualização do sistema operacional  <br/> |Se forem necessárias regras mais restritivas, veja as seguintes URLs de lista de permissões:  <br/> |Windows Update  <br/> WSUS  <br/> |
|Atualização de aplicativos  <br/> |Windows Store  <br/> |Windows Store  <br/> Configuration Manager  <br/> |
|Configuração da Conta  <br/> |Centro de administração do Teams  <br/> |Centro de administração do Teams  <br/> |
|Acesso aos logs  <br/> |Centro de administração do Teams  <br/> Powershell  <br/> |Centro de administração do Teams <br/> Powershell  <br/>  |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Configurando Política de Grupo para Salas do Microsoft Teams
<a name="GroupPolicy"> </a>

Esta seção aborda as configurações do sistema das quais Salas do Microsoft Teams depende para funcionar corretamente. 

Ingressar no Salas do Teams a um domínio do Active Directory oferece os seguintes benefícios:

- A associação de domínio Salas do Teams permite que você conceda direitos administrativos a usuários e grupos de domínio. Ao fazer isso, você não precisará ter que se lembrar da senha da conta do administrador no nível da máquina local.

- Você pode implantar a configuração de Qualidade de Serviço do Windows Salas do Teams.

- Se estiver Skype for Business, ingressar no domínio Salas do Teams automatizará a importação da cadeia de certificados raiz privada da sua organização.

Ao ingressar o Salas do Teams em um domínio, é necessário criar uma UO (Unidade Organizacional) separada para que você possa fornecer exclusões de GPO (objeto Política de Grupo) à UO em que todos os objetos Salas do Teams residem. Desabilite toda a herança de GPO para que Política de Grupo configurações sem suporte não seja aplicada a Salas do Teams. Crie objetos de computador na UO antes de Salas do Teams ao domínio para garantir que as Políticas de Grupo aplicadas à UO de computadores padrão não sejam aplicadas.

> [!NOTE]
> Mesmo que você crie uma UO separada e bloqueie a herança, há algumas políticas de grupo que podem causar problemas se elas não tiverem nenhuma substituição definida. Um Política de Grupo conjunto sem substituição vence uma UO com Herança de Política de Bloco definida.

Muitas organizações têm os GPOs a seguir, que afetam Salas do Teams funcionalidade. Certifique-se de substituir ou bloquear a herança destes:

  - Tempo limite de sessões de logon (bloqueio automático)
  - Políticas relacionadas ao gerenciamento de energia
  - Requerendo etapas adicionais de autenticação
  - Negando acesso a unidades locais
  - Avisando usuários para conexões de rede lentas
  - Iniciar um determinado programa no logon
  - Crie uma outra conta de usuário de domínio em todas as máquinas que ingressaram no domínio.
  - Enviar Windows Update para Salas do Teams

Ao ingressar Salas do Microsoft Teams a um domínio, verifique se as políticas de grupo não substituem as configurações na tabela a seguir.

|Configuração|Permite|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Habilita Salas do Microsoft Teams inicialização  <br/> |
|Gerenciamento de Energia –\> No AC, desative a tela após 10 minutos  <br/> Gerenciamento de Energia –\> No AC, nunca coloque o sistema em sono  <br/> |Permite Salas do Microsoft Teams desativar as exibições anexadas e ativar automaticamente  <br/> |
|net accounts /maxpwage:unlimited  <br/> Ou um modo equivalente de desabilitar a expiração da senha na conta local. A impossibilidade de fazer isso pode causar uma falha no logon com a conta do Skype com uma mensagem de senha expirada. Observe que isso afeta todas as contas locais do computador. Portanto, se isso não for definido, com o tempo, a conta de administrador também vai expirar.   <br/> |Permite que a conta do Skype esteja sempre conectada  <br/> |

> [!NOTE]
> Quando Salas do Microsoft Teams for compatível com a próxima versão do sistema operacional Windows 10, o Salas do Teams será atualizado automaticamente para a próxima versão por meio Windows Update. O Salas do Microsoft Teams não deve ser atualizado para a próxima versão do Windows 10 manualmente ou por meio da habilitação de políticas de grupo do Windows Update for Business (WUFB) "Selecione o nível de preparação do Windows para as atualizações que você deseja receber" e "Selecione quando builds de visualização e recursos Atualizações são recebidos" por meio do GPO. Salas do Teams com essas políticas de grupo habilitadas é conhecida por ter problemas com Windows 10 do sistema operacional.

## <a name="remote-management-using-powershell"></a>Gerenciamento remoto usando o PowerShell
<a name="RemotePS"> </a>

Você pode executar as seguintes operações de gerenciamento remotamente usando o PowerShell (consulte a tabela abaixo para obter exemplos de script):
  
- Obter dispositivos conectados
- Obter o status do aplicativo
- Obter informações do sistema
- Reiniciar o sistema
- Recuperar logs
- Transferir arquivos (requer um grupo de Salas do Microsoft Teams)
    
> [!NOTE]
> Essa funcionalidade está desativada por padrão. Você precisa habilitar o PowerShell remoto para seu ambiente no Salas do Microsoft Teams para executar as operações abaixo. Consulte a documentação sobre **[Enable-PSRemoting para obter](/powershell/module/microsoft.powershell.core/enable-psremoting)** informações sobre como habilitar o PowerShell remoto.
  
Por exemplo, você pode habilitar o PowerShell Remoto da seguinte maneira:
  
1. Entre como Administração em um Salas do Microsoft Teams dispositivo.
2. Abra um prompt de comando do PowerShell com privilégios elevados.
3. Insira o seguinte comando: `Enable-PSRemoting -SkipNetworkProfileCheck -Force`
4. Abra a Política de Segurança Local e adicione ogrupo de *segurança Administradores*  >  >  >  à Atribuição de Direitos de Usuário de Políticas Locais de Configurações **de Segurança. Acesse este computador da rede**.

Para executar uma operação de gerenciamento:
  
1. Entre em um computador com credenciais de conta que tenham permissão para executar comandos do PowerShell em um Salas do Microsoft Teams dispositivo.
2. Abra um prompt de comando regular do PowerShell no computador.
3. Copie o texto do comando da tabela abaixo e cole-o no prompt.
4. Substitua  `<Device fqdn>` os campos por valores de FQDN apropriados ao seu ambiente.
5. Substitua  *\<path\>*  pelo nome do arquivo e pelo caminho local do arquivo de configuração SkypeSettings.xml mestre (ou imagem de tema).
    
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

Enviar por push um arquivo de configuração XML (ou gráfico de tema)
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>Atualizações de software
<a name="SWupdate"> </a>

Por padrão, Salas do Microsoft Teams se conecta ao Windows Update para recuperar atualizações de firmware do dispositivo periférico USB e do sistema operacional e as instala fora do horário comercial configurado. Você pode configurar o horário comercial entrando na conta de administrador e executando **o aplicativo Configurações** .
  
Se você quiser gerenciar as atualizações manualmente e não conseguir seguir o procedimento normal do [Microsoft Store para Empresas](https://businessstore.microsoft.com/store) para distribuir aplicativos [offline](/microsoft-store/distribute-offline-apps), poderá adquirir e executar o script MTR-Update mais recente de um dispositivo Salas do Microsoft Teams [manualmente](/microsoftteams/rooms/manual-update).

Por padrão, Salas do Microsoft Teams tenta se conectar à Windows Store para obter a versão mais recente do Salas do Microsoft Teams software. Portanto, Salas do Teams requer acesso regular à Internet. Antes de entrar em contato com a Microsoft com problemas de suporte, verifique se Salas do Microsoft Teams está carregado com a versão mais recente do aplicativo.



## <a name="admin-mode-and-device-management"></a>Modo de administração e gerenciamento de dispositivo
<a name="AdminMode"> </a>

Algumas funções de gerenciamento, como instalar manualmente um certificado de autoridade de certificação privado, exigem Salas do Teams no Administração privado. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>Alternar para o Administração e voltar quando o aplicativo Salas do Microsoft Teams está em execução

1. Desligue todas as chamadas em andamento e retorne à tela inicial.
2. Selecione o ícone de engrenagem e abra o menu (as opções são **Configurações**, **Acessibilidade** e **Reiniciar Dispositivo** ).
3. Selecione **Configurações**.
4. Insira a senha do Administrador. A tela Configuração será exibida.  Se o dispositivo não estiver ingressado no domínio, a conta administrativa local (nome de usuário "Administração") será usada por padrão. A senha padrão dessa conta é 'sfb'. Altere essa senha assim que possível. Se o computador estiver ingressado no domínio, você poderá entrar com uma conta de domínio com privilégios apropriados.
5. Selecione **Configurações do Windows** na coluna à esquerda.
6. Faça logon no desktop usando as credenciais administrativas. Você terá os privilégios necessários para gerenciar o dispositivo.
7. Execute as tarefas administrativas necessárias.
8.  Reinicie o computador quando terminar.
    
O console retorna ao seu modo de operação normal. O procedimento a seguir exige que você conecte um teclado ao dispositivo, caso ele esteja sem.  
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>Alternar para o Administração e voltar quando o aplicativo Salas do Microsoft Teams falha

1. Pressione a tecla do Windows cinco vezes em uma sucessão rápida. Isso levará você para a tela de logon do Windows. 
2. Faça logon no desktop usando as credenciais administrativas.
3. Execute as tarefas administrativas necessárias.
4. Reinicie o computador quando terminar.

    > [!NOTE]
    > Esse método não faz logoff do usuário do Skype ou encerra normalmente o aplicativo, mas você o usaria se o aplicativo não estivesse respondendo e o outro método não estivesse disponível. 

   O console é reiniciado em seu modo de operação normal, executando o Salas do Microsoft Teams aplicativo. Você poderá remover o teclado se tiver anexado um para concluir este procedimento.
   ## <a name="troubleshooting-tips"></a>Dicas para solução de problemas
   <a name="TS"> </a>

- Os convites de reunião podem não aparecer quando enviados entre limites de domínio (por exemplo, entre duas empresas). Nesses casos, os administradores de TI devem decidir se permitem que usuários externos agendem uma reunião. Consulte o artigo para o cmdlet [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing) do Exchange PowerShell, especificamente o parâmetro 'ProcessExternalMeetingMessages'.
- Salas do Microsoft Teams dá suporte a redirecionamentos de Descoberta Automática do Exchange por meio do Exchange 2010.
- Em geral, é uma boa prática para os administradores de TI desabilitar os pontos de extremidade de áudio que eles não pretendem usar.
- No caso de uma imagem espelhada ser exibida na visualização da sala, o administrador de TI poderá corrigir com o ciclo de energia da câmera ou invertendo a orientação da imagem usando as configurações da câmera.
- Sabe-se que pode ocorrer a perda do acesso à tela touch do console. Nesses casos, o problema às vezes é resolvido reiniciando Salas do Teams.
- Sabe-se que pode ocorrer a perda do áudio local ao conectar um computador ao console via entrada com fio. Nesses casos, reiniciar o computador pode resolver o problema de reprodução do áudio local.
