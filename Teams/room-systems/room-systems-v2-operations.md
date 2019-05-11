---
title: Operações e manutenção de salas de equipes da Microsoft
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
ms.collection: M365-voice
localization_priority: Normal
description: Leia este tópico para saber mais sobre o gerenciamento de salas de equipes da Microsoft, a próxima geração de sistemas de sala Skype.
ms.openlocfilehash: 384920dc64d16dd9a50d7eee6e8546ad9920044e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33916324"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Operações e manutenção de salas de equipes da Microsoft 
 
Leia este tópico para saber mais sobre o gerenciamento de salas de equipes da Microsoft, a próxima geração de sistemas de sala Skype.
  
Salas de equipes da Microsoft é a solução de conferência mais recente da Microsoft projetada para transformar a sala de reunião em uma experiência rica e colaborativa. Os usuários aproveitarão seu familiar Teams da Microsoft ou Skype para interface de negócios e os administradores de TI apreciará um aplicativo de reunião do Windows 10 Skype facilmente implantado e gerenciado. Salas de equipes da Microsoft foi projetada para aproveitar o equipamento existente como painéis LCD para facilitar da instalação para trazer Teams da Microsoft ou Skype for Business para sala de reunião.
  
Com uma configuração adicional, gerenciamento remoto é possível usando o Microsoft Azure Monitor conforme descrito em [gerenciamento de planejar salas de equipes da Microsoft com o Azure Monitor](azure-monitor-plan.md), [gerenciamento de implantar o Microsoft equipes salas com Monitor do Azure](azure-monitor-deploy.md), [Gerenciar Dispositivos de salas de equipes da Microsoft com o Azure Monitor](azure-monitor-deploy.md). Você também pode [Gerenciar salas de equipes da Microsoft configurações remotamente com um arquivo de configuração XML do console](xml-config-file.md), que inclui a aplicação de um tema de exibição personalizado. 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Como salvar logs em salas de equipes da Microsoft
<a name="Logs"> </a>

Para coletar logs, você deve chamar o script de conjunto de log que acompanha o aplicativo Microsoft equipes salas. No modo Admin, inicie um prompt de comandos com privilégios elevados e emita o seguinte comando:
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

Os logs serão exibidos como um arquivo ZIP em c:\rigel.
  
## <a name="front-of-room-display-settings"></a>Configurações da tela frontal da sala
<a name="Display"> </a>

Configure a tela frontal da sala para o modo Estendido. Isso garantirá que o console de que interface do usuário não é duplicado em que exiba quando você desligue a exibição.
  
> [!NOTE]
> A TV usada em uma sala de exibição precisa suportar/habilitar o recurso CEC (Controle Eletrônico do Consumidor) do HDMI para que possa alternar automaticamente do modo de espera para uma fonte de vídeo ativa.  Esse recurso não é suportado em todas as TVs. 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Redefinição de salas de equipes da Microsoft (restauração de fábrica)
<a name="Reset"> </a>

Se salas de equipes da Microsoft não está funcionando bem, realizar uma restauração de fábrica pode ajudar. Isso pode ser feito no aplicativo configurações na guia **recuperação** abaixo **Redefinir este PC**, selecione **começar**e **Remover tudo**. Siga as instruções restantes para redefinir o dispositivo.
  
> [!NOTE]
> Há um problema conhecido onde as salas de equipes da Microsoft podem se tornar disponível se a opção **Manter Meus arquivos - remove aplicativos e configurações, mas mantém os arquivos pessoais** está selecionada durante o processo de redefinição do Windows. Faça _não_ use esta opção.
  
## <a name="supported-remote-options"></a>Opções remotas com suporte
<a name="RemoteOptions"> </a>

A tabela a seguir resume as operações remotas possíveis e os métodos que você pode usar para executá-las.
  

|**Grupo de trabalho **|**Não ingresso em domínio**|**Ingresso em domínio**|
|:-----|:-----|:-----|
|Reiniciar  <br/> |Área de trabalho remota  <br/> PowerShell Remoto  <br/> |Área de trabalho remota (requer configuração adicional)  <br/> Powershell remoto (requer configuração adicional)  <br/> SCCM  <br/> |
|Atualização do sistema operacional  <br/> |Se forem necessárias regras mais restritivas, veja as seguintes URLs de lista de permissões:  <br/> |Windows Update  <br/> WSUS  <br/> |
|Atualização de aplicativos  <br/> |Windows Store  <br/> |Windows Store  <br/> SCCM  <br/> |
|Configuração de contas do Skype  <br/> |Sem suporte no momento  <br/> |Sem suporte no momento  <br/> |
|Acesso aos logs  <br/> |Sem suporte no momento  <br/> |Sem suporte no momento  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Configurando a diretiva de grupo para salas de equipes da Microsoft
<a name="GroupPolicy"> </a>

Esta seção aborda as configurações do sistema Microsoft equipes salas depende funcione corretamente. Ao ingressar em salas de equipes da Microsoft a um domínio, certifique-se de que sua política de grupo não substituem as definições na tabela a seguir.
  

|**Configuração**|**Permite**|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Permite que o Microsoft salas de equipes inicialize  <br/> |
|Gerenciamento - de energia\> nas AC, desative tela após 10 minutos  <br/> Gerenciamento - de energia\> em AC, nunca colocar o sistema no modo de suspensão  <br/> |Habilita a salas de equipes da Microsoft desativar exibe anexado e automaticamente de ativação  <br/> |
|net accounts /maxpwage:unlimited  <br/> Ou equivalentes meios de desativação de expiração de senha da conta local. Falha ao fazer isso, eventualmente, fará com que a conta do Skype falha de logon reclamando uma senha expirada. Observe que isso afeta todas as contas locais na máquina, e assim falha configurar isso também fará com que a conta administrativa na caixa eventualmente expire também.  <br/> |Permite que a conta do Skype esteja sempre conectada  <br/> |
   
Transferência de arquivos usando diretivas de grupo será discutido em [Configure um Item do arquivo](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).
  
## <a name="remote-management-using-powershell"></a>Gerenciamento remoto usando o PowerShell
<a name="RemotePS"> </a>

Você pode executar as seguintes operações de gerenciamento remotamente usando o PowerShell (consulte a tabela abaixo para amostras de script):
  
- Obter dispositivos conectados
    
- Obter o status do aplicativo
    
- Obter informações do sistema
    
- Reiniciar o sistema
    
- Recuperar logs
    
- Transferir arquivos (requer um salas de equipes do Microsoft associados a um domínio)
    
> [!NOTE]
> Essa funcionalidade está desativada por padrão. Você precisa ativar o PowerShell remoto para o seu ambiente no sistema de salas de equipes da Microsoft executar as operações abaixo. Consulte a documentação sobre **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** para obter informações sobre como habilitar o PowerShell remoto.
  
Por exemplo, você pode habilitar o PowerShell Remoto da seguinte maneira:
  
1. Entrar como administrador em um dispositivo de salas de equipes da Microsoft.
    
2. Abra um prompt de comando do PowerShell.
    
3. Insira o seguinte comando: Enable-PSRemoting -force
    
Para executar uma operação de gerenciamento:
  
1. Entrar em um PC com credenciais de conta que tem permissão para executar comandos do PowerShell em um dispositivo de salas de equipes da Microsoft.
    
2. Abra um prompt de comando do PowerShell regular no PC.
    
3. Copie o texto de comando da tabela a seguir e cole-o no prompt.
    
4. Substituir `<Device fqdn>` campos com valores FQDN apropriadas ao seu ambiente.
    
5. Substituir * \<caminho\> * com o nome de arquivo e o caminho local do arquivo de configuração SkypeSettings.xml mestre (ou imagem de tema).
    
Para obter os dispositivos conectados
  
```
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

Obter o status de aplicativos
  
```
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

Obter informações do sistema
  
```
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

Reiniciar o sistema
  
```
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

Recuperar logs
  
```
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

Enviar um arquivo de configuração XML (ou o gráfico do tema)
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>Atualizações de software
<a name="SWupdate"> </a>

Por padrão, o Microsoft equipes salas tenta se conectar ao repositório do Windows para obter a versão mais recente do software de salas de equipes da Microsoft, para que o dispositivo exigirá regular acesso à internet. Antes de contatar o Microsoft com problemas de suporte, certifique-se de que o dispositivo de salas de equipes da Microsoft é carregado com a versão mais recente do aplicativo.
  
Por padrão, salas de equipes da Microsoft se conecta ao Windows Update para recuperar o sistema operacional e atualizações de firmware de dispositivos periféricos USB e as instala fora do horário de comercial configurado. Para configurar o horário comercial, entre na conta de administrador e execute o aplicativo Configurações.
  
Se você deseja gerenciar atualizações manualmente e não conseguem siga o procedimento de normal para [Microsoft Store for Business](https://businessstore.microsoft.com/store) para [distribuir aplicativos de offline](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), você pode adquirir as arquivo APPX apropriado e dependências do [kit de implantação](https://go.microsoft.com/fwlink/?linkid=851168) (de as instruções para [Configurar um console de salas de equipes da Microsoft](console.md)) que podem ser usados com o SCCM. A versão do kit de implantação sofra a versão do repositório, portanto pode não sempre corresponder a compilação mais recente disponível.
  
### <a name="to-update-using-powershell"></a>Para atualizar usando Powershell

1. Extraia o pacote da instalação [MSI](https://go.microsoft.com/fwlink/?linkid=851168) para um compartilhamento de dispositivo pode acessar.
    
2. Execute o seguinte script direcionando os dispositivos de salas de equipes da Microsoft, alterando \<compartilhar\> ao dispositivo compartilhar conforme apropriado:
    
```
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a>Modo de administração e gerenciamento de dispositivo
<a name="AdminMode"> </a>

Algumas funções de gerenciamento, como manualmente instalando um certificado de autoridade de certificação privado, exigem colocando o dispositivo Surface Pro no modo de administrador. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>Alternando para o modo de administração e voltar quando o aplicativo de salas de equipes da Microsoft está sendo executado

1. Desligar todas as chamadas em andamento e retornar à tela inicial.
    
2. Selecione o ícone de engrenagem e acessar o menu (opções estarão **configurações**, **acessibilidade**e **Reinicie o dispositivo** ).
    
3. Selecione **Configurações**.
    
4. Digite a senha do administrador. A tela Configuração será exibida.
    
    > [!NOTE]
    > Se o dispositivo não estiver associado ao domínio, a conta administrativa local (username "Admin") será usada por padrão. A senha padrão para essa conta será 'sfb', mas é recomendável que sua organização mude essa senha o quanto antes por motivos de segurança. Se o computador estiver associado ao domínio, você pode entrar com uma conta de domínio apropriadamente privilegiado. 
  
5. Selecione **Configurações do Windows** , na coluna esquerda.
    
6. Escolha **Vá para Entrada como Admin**.
    
7. Digite a senha do administrador. Isso faz com que o aplicativo seja desativado e leva você até a tela de logon do Windows. 
    
8. Faça logon no desktop usando as credenciais administrativas. Você terá os privilégios necessários para gerenciar o dispositivo.
    
9. Execute as tarefas administrativas necessárias.
    
10. Saia da conta de Administrador.
    
11. Retorne à Microsoft equipes salas selecionando o ícone de conta de usuário no lado esquerdo da tela e, em seguida, selecionando **Skype**.
    
    Se o usuário **Skype** não estiver listado, você pode precisar selecionar **outro usuário** e insira **. \skype** como o nome de usuário e de entrada.
    
O console agora é novamente em seu modo de operação normal. O procedimento a seguir exige que você anexar um teclado para o dispositivo, se ainda não estiver já anexado. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>Alternando para o modo de administração e quando o aplicativo Microsoft equipes salas de travamento

1. Pressione a tecla do Windows cinco vezes em uma sucessão rápida. Isso levará você para a tela de logon do Windows. 
    
2. Faça logon no desktop usando as credenciais administrativas.
    
    > [!NOTE]
    > Esse método não logoff do usuário do Skype ou finalizado normalmente o aplicativo, mas você deve usá-lo se o aplicativo não estava respondendo e o outro método não estava disponível. 
  
3. Execute as tarefas administrativas necessárias.
    
4. Quando tiver terminado, reinicie a máquina.
    
   O console é reiniciado em seu modo de operação normal, executando o aplicativo Microsoft equipes salas. Você pode remover o teclado, se ele foi conectado para permitir que você executar esse procedimento.
   ## <a name="troubleshooting-tips"></a>Dicas para solução de problemas
   <a name="TS"> </a>

- Convites de reunião podem não aparecer quando enviado nos limites do domínio (por exemplo, entre as duas empresas). Nesses casos, os administradores de TI devem decidir se deseja permitir que usuários externos agendar uma reunião.
    
- Salas de equipes da Microsoft não suporta os redirecionamentos de descoberta automática do Exchange por meio do Exchange 2010.
    
- Em geral, é uma boa prática para administradores de TI desabilitar quaisquer pontos de extremidade de áudio não pretendem usar.
    
- Caso seja exibida uma imagem espelhada na visualização da sala, o administrador de TI pode corrigir isso desligando e ligando a câmera ou invertendo a orientação da imagem com o controle remoto da câmera.
    
- Sabe-se que pode ocorrer a perda do acesso à tela touch do console. Nesses casos, o problema em alguns casos, é resolvido reiniciando-se o sistema de salas de equipes da Microsoft.
    
- Sabe-se que pode ocorrer a perda do áudio local ao conectar um computador ao console via entrada com fio. Nesses casos, reiniciar o computador pode resolver o problema de reprodução do áudio local.
    
