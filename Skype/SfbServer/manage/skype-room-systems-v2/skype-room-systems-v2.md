---
title: Gerenciar o Skype Room Systems versão 2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
description: Leia este tópico para saber mais sobre o gerenciamento de sistemas de sala Skype v2, a próxima geração de sistemas de sala Skype.
ms.openlocfilehash: 562dbeea19fb732caf9348e2bfd632da3579e71a
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/05/2018
---
# <a name="manage-skype-room-systems-v2"></a>Gerenciar o Skype Room Systems versão 2
 
Leia este tópico para saber mais sobre o gerenciamento de sistemas de sala Skype v2, a próxima geração de sistemas de sala Skype.
  
Sistemas de sala Skype v2 é a solução de conferência mais recente da Microsoft projetada para transformar a sala de reunião em um Skype rica e colaboração para a experiência de negócios. Os usuários apreciarão a interface familiar do Skype for Business, e os administradores de TI ficarão satisfeitos com a implantação e o gerenciamento fáceis do aplicativo Reunião do Skype para Windows 10. Sistemas de sala Skype v2 foi projetado para aproveitar o equipamento existente como painéis LCD para facilitar da instalação para trazer Skype for Business para sala de reunião.
  
Com uma configuração adicional, gerenciamento remoto é possível usando o pacote de gerenciamento de operações da Microsoft (OMS) conforme descrito em [sistemas de sala Skype planejar gerenciamento de v2 com OMS](../../plan-your-deployment/clients-and-devices/oms-management.md), [gerenciamento de v2 implantar sistemas do Skype sala com OMS](../../deploy/deploy-clients/with-oms.md)e [Gerenciar Dispositivos de v2 de sistemas de sala Skype com OMS](oms.md). Você também pode [Gerenciar um v2 de sistemas de sala Skype configurações de console remotamente com um arquivo de configuração XML](xml-config-file.md), que inclui a aplicação de um tema de exibição personalizado. 
  
## <a name="collecting-logs-on-skype-room-systems-v2"></a>Coletando logs no Skype Room Systems versão 2
<a name="Logs"> </a>

Para coletar logs, você deve chamar o script de conjunto de log que acompanha o aplicativo de v2 Skype sistemas de sala. No modo Admin, inicie um prompt de comandos com privilégios elevados e emita o seguinte comando:
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

Os logs serão exibidos como um arquivo ZIP em c:\rigel.
  
## <a name="front-of-room-display-settings"></a>Configurações da tela frontal da sala
<a name="Display"> </a>

Configure a tela frontal da sala para o modo Estendido. Isso garante que a interface do usuário do console não seja duplicada nessa tela ao desligar e ligar a tela.
  
> [!NOTE]
> A TV usada em uma sala de exibição precisa suportar/habilitar o recurso CEC (Controle Eletrônico do Consumidor) do HDMI para que possa alternar automaticamente do modo de espera para uma fonte de vídeo ativa.  Esse recurso não é suportado em todas as TVs. 
  
## <a name="skype-room-systems-v2-reset-factory-restore"></a>Redefinição do Skype Room Systems versão 2 (restauração de fábrica)
<a name="Reset"> </a>

Se a sistemas de sala Skype v2 não está funcionando bem, realizar uma restauração de fábrica pode ajudar. Isso pode ser feito no aplicativo configurações da guia "Recuperação" sob o cabeçalho "Redefinir essa PC", selecione "Introdução" seguido por "Remover tudo". Siga os avisos seguintes conforme desejado para redefinir o dispositivo.
  
> [!NOTE]
> Há um problema conhecido onde o v2 Skype sala sistemas podem se tornar disponível se a opção "Manter meus arquivos - remove os aplicativos e configurações, mas mantém seus arquivos pessoais" for selecionada durante o processo de redefinição do Windows. **Não** use essa opção.
  
## <a name="supported-remote-options"></a>Opções remotas com suporte
<a name="RemoteOptions"> </a>

A tabela a seguir resume as operações remotas possíveis e os métodos que você pode usar para executá-las.
  

|**Grupo de trabalho**|**Não unido ao domínio**|**Ingressado no domínio**|
|:-----|:-----|:-----|
|Reiniciar  <br/> |Área de trabalho remota  <br/> PowerShell Remoto  <br/> |Área de trabalho remota (requer configuração adicional)  <br/> Powershell remoto (requer configuração adicional)  <br/> SCCM  <br/> |
|Atualização do sistema operacional  <br/> |Windows Update  <br/> |Windows Update  <br/> WSUS  <br/> |
|Atualização de aplicativos  <br/> |Windows Store  <br/> |Windows Store  <br/> SCCM  <br/> |
|Configuração de contas do Skype  <br/> |Sem suporte no momento  <br/> |Sem suporte no momento  <br/> |
|Acesso aos logs  <br/> |Sem suporte no momento  <br/> |Sem suporte no momento  <br/> |
   
## <a name="configuring-group-policy-for-skype-room-systems-v2"></a>Configurando a Política de Grupo para o Skype Room Systems versão 2
<a name="GroupPolicy"> </a>

Esta seção aborda as configurações do sistema que sistemas de sala Skype v2 depende funcione corretamente. Ao ingressar em sistemas de sala Skype v2 para um domínio, certifique-se de que sua política de grupo não substitui as configurações a seguir:
  

|**Configuração**|**Permite**|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AdminAutoLogon = (dword) 1  <br/> |Permite que os sistemas de sala Skype v2 inicialize  <br/> |
|Gerenciamento - de energia\> nas AC, desative tela após 10 minutos  <br/> Gerenciamento - de energia\> em AC, nunca colocar o sistema no modo de suspensão  <br/> |Permite que os sistemas de sala Skype v2 desativar exibe anexado e automaticamente de ativação  <br/> |
|net accounts /maxpwage:unlimited  <br/> Ou equivalentes meios de desativação de expiração de senha da conta local. Falha ao fazer isso, eventualmente, fará com que a conta do Skype falha de logon reclamando uma senha expirada. Observe que isso afeta todas as contas locais na máquina, e assim falha configurar isso também fará com que a conta administrativa na caixa eventualmente expire também.  <br/> |Permite que a conta do Skype esteja sempre conectada  <br/> |
   
Transferência de arquivos usando diretivas de grupo será discutido em [Configure um Item do arquivo](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).
  
## <a name="remote-management-using-powershell"></a>Gerenciamento remoto usando o PowerShell
<a name="RemotePS"> </a>

Você pode realizar a seguintes operações de gerenciamento remotamente usando o PowerShell (veja exemplos de scripts na tabela a seguir):
  
- Obter dispositivos conectados
    
- Obter o status do aplicativo
    
- Obter informações do sistema
    
- Reiniciar o sistema
    
- Recuperar logs
    
- Transferir arquivos (requer um domínio ingressou Skype sala sistemas v2)
    
> [!NOTE]
> Essa funcionalidade está desativada por padrão. Você precisa ativar o PowerShell remoto para o seu ambiente no sistema sistemas de sala Skype v2 executar as operações abaixo. Consulte a documentação sobre **[Enable-PSRemoting](https://technet.microsoft.com/en-us/library/hh849694.aspx)** para obter informações sobre como habilitar o PowerShell remoto.
  
Por exemplo, você pode habilitar o PowerShell Remoto da seguinte maneira:
  
1. Entrar como administrador em um dispositivo de v2 Skype sistemas de sala.
    
2. Abra um prompt de comando do PowerShell com privilégios elevados.
    
3. Insira o seguinte comando: Enable-PSRemoting - forçar
    
Para executar uma operação de gerenciamento:
  
1. Inscreva-se em um PC com credenciais de conta que tem permissão para executar comandos do PowerShell em um dispositivo de v2 Skype sistemas de sala.
    
2. Abra um prompt de comando normal do PowerShell em seu computador.
    
3. Copie o texto do comando da tabela a seguir e cole-o no prompt.
    
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

Enviar por push um arquivo de configuração XML ou elemento gráfico do tema)
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>Atualizações de software
<a name="SWupdate"> </a>

Por padrão, os sistemas de sala Skype v2 tentará se conectar ao repositório do Windows para obter a versão mais recente do software do Skype sala sistemas v2, portanto, o dispositivo exigirá regular acesso à internet. Certifique-se de que o dispositivo do Skype sala sistemas v2 é carregado com a versão mais recente do aplicativo, antes de contatar o Microsoft com problemas de suporte.
  
Por padrão, o Skype sala sistemas v2 conectar ao Windows Update para recuperar o sistema operacional, bem como o firmware de periféricos USB atualizações e instalá-los fora do horário de comercial configurado. Para configurar o horário comercial, entre na conta de administrador e execute o aplicativo Configurações.
  
Se você deseja gerenciar atualizações manualmente e não conseguem siga o procedimento de normal para [Microsoft Store for Business](https://businessstore.microsoft.com/en-us/store) para [distribuir aplicativos de offline](https://docs.microsoft.com/en-us/microsoft-store/distribute-offline-apps), você pode adquirir as arquivo APPX apropriado e dependências do [kit de implantação](https://go.microsoft.com/fwlink/?linkid=851168) (de as instruções para [Configurar um console do Skype sala sistemas v2](../../deploy/deploy-clients/console.md)) que podem ser usados com o SCCM. O lançamento do kit de implantação é feito depois do lançamento da loja, portanto nem sempre a versão adquirida corresponde à versão mais recente disponível.
  
### <a name="to-update-using-powershell"></a>Para atualizar usando Powershell

1. Extraia o pacote da instalação [MSI](https://go.microsoft.com/fwlink/?linkid=851168) para um compartilhamento acessível do dispositivo.
    
2. Execute o seguinte script direcionando os dispositivos de v2 Skype sala sistemas, alterando \<compartilhar\> ao dispositivo compartilhar conforme apropriado:
    
  ```
  Add-AppxPackage -Update -ForceApplicationShutdown -Path \\<share>\Rigel\x64\Ship\AppPackages\*\*.appx -DependencyPath (Get-ChildItem \\<share>\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx | Foreach-Object {$_.FullName}) 

  ```

## <a name="admin-mode-and-device-management"></a>Modo de administração e gerenciamento de dispositivo
<a name="AdminMode"> </a>

Algumas funções de gerenciamento, como a instalação manual de um certificado de autoridade de certificação privado, exige que o dispositivo Surface 4 seja colocado no modo Admin.  
  
### <a name="switching-to-admin-mode-and-back-when-the-skype-room-systems-v2-app-is-running"></a>Alternando para o modo de administração e voltar quando o aplicativo do Skype sala sistemas v2 está sendo executado

1. Desligar quaisquer chamadas de saída e retornar para a tela inicial.
    
2. Clique no ícone de engrenagem e acessar o menu (opções estarão **configurações**, **acessibilidade**e **Reinicie o dispositivo** ).
    
3. Selecione **Configurações**.
    
4. Digite a senha do administrador. A tela Configuração será exibida.
    
    > [!NOTE]
    > Se o dispositivo não ingressou no domínio, a conta administrativa local (nome de usuário "Admin") será usada por padrão. A senha padrão para essa conta será 'sfb', mas é recomendável que sua organização mude essa senha o quanto antes por motivos de segurança. Se o computador ingressou no domínio, você pode entrar com uma conta de domínio com os privilégios adequados. 
  
5. Clique em **Configurações do Windows** na coluna da esquerda.
    
6. Escolha **Vá para Entrada como Admin**.
    
7. Digite a senha do administrador. Isso faz com que o aplicativo seja desativado e leva você até a tela de logon do Windows. 
    
8. Faça logon no desktop usando as credenciais administrativas. Você terá os privilégios necessários para gerenciar o dispositivo.
    
9. Execute as tarefas administrativas necessárias.
    
10. Saia da conta de Administrador.
    
11. Retornar a sistemas de sala Skype v2 selecionando o ícone de conta de usuário na extremidade esquerda da tela e selecione **Skype**.
    
    Se o usuário **Skype** não estiver listado, você pode precisar selecionar **outro usuário** e insira **. \skype** como o nome de usuário e de entrada.
    
 O console agora é novamente em seu modo de operação normal. O procedimento a seguir exige que você anexar um teclado para o dispositivo, se ainda não estiver já anexado. 
  
### <a name="switching-to-admin-mode-and-back-when-the-skype-room-systems-v2-app-crashes"></a>Alternando para o modo de administração e quando o aplicativo do Skype sala sistemas v2 cai

1. Pressione a tecla do Windows cinco vezes em uma sucessão rápida. Isso levará você para a tela de logon do Windows.  
    
2. Faça logon no desktop com as credenciais administrativas.
    
    > [!NOTE]
    > Esse método não desconecta o usuário do Skype nem encerra o aplicativo, mas ele só deve ser usado quando o aplicativo não estiver respondendo e outro método não estiver disponível. 
  
3. Execute as tarefas administrativas necessárias.
    
4. Reinicie o computador ao terminar.
    
 O console é reiniciado em seu modo de operação normal, executando o aplicativo de v2 Skype sistemas de sala. Você pode remover o teclado, caso ele tenha sido conectado para executar esse procedimento.
## <a name="troubleshooting-tips"></a>Dicas para solução de problemas
<a name="TS"> </a>

- Talvez os convites de reuniões não sejam exibidos quando enviados de fora dos limites do domínio (por exemplo, entre duas empresas). Nesses casos, os administradores de TI devem decidir se usuários externos terão permissão para agendar reuniões.
    
- Sistemas de sala Skype v2 não suporta os redirecionamentos de descoberta automática do Exchange por meio do Exchange 2010.
    
- Em geral, é recomendável que os administradores de TI desabilitem todos os pontos de extremidade de áudio que não se pretende usar.
    
- Caso seja exibida uma imagem espelhada na visualização da sala, o administrador de TI pode corrigir isso desligando e ligando a câmera ou invertendo a orientação da imagem com o controle remoto da câmera.
    
- Sabe-se que pode ocorrer a perda do acesso à tela touch do console. Nesses casos, o problema em alguns casos, é resolvido reiniciando-se o sistema de v2 Skype sistemas de sala.
    
- Sabe-se que pode ocorrer a perda do áudio local ao conectar um computador ao console via entrada com fio. Nesses casos, reiniciar o computador pode resolver o problema de reprodução do áudio local.
    
## <a name="see-also"></a>Ver também
<a name="TS"> </a>

#### 

[Planejar a sala Skype v2 de sistemas](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Implantar Skype sala v2 de sistemas](../../deploy/deploy-clients/room-systems-v2.md)
  
[Configurar um console v2 de sistemas de sala do Skype](../../deploy/deploy-clients/console.md)
  
[Gerenciar configurações de sistemas de sala Skype do console v2 remotamente com um arquivo de configuração XML](xml-config-file.md)

