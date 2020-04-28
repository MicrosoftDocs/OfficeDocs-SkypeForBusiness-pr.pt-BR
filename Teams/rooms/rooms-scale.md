---
title: Implantar salas do Microsoft Teams usando o Gerenciador de configuração do Microsoft Endpoint
author: lanachin
ms.author: v-lanac
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: Saiba mais sobre a implantação de salas do Microsoft Teams em implantações em grandes escalas usando o Gerenciador de configuração do Microsoft Endpoint.
no-loc:
- Microsoft
- Microsoft Corporation
- Microsoft Teams Rooms
- Microsoft Teams Room
- System Center
- Configuration Manager
- Windows
- Surface
- Surface Pro
- Windows PE
- Windows 10
- Windows 10 Enterprise
- Azure
- Azure Monitor
- Log Analytics
- Operations Management Suite
ms.openlocfilehash: f96b970165996cc27308ce616fb4875d741f8869
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905313"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a>Implantar salas do Microsoft Teams usando o Gerenciador de configuração do Microsoft Endpoint

Este artigo fornece todas as informações necessárias para criar suas implantações de salas do Microsoft Teams usando o Gerenciador de configuração do Microsoft Endpoint.

Com os métodos fáceis de usar fornecidos pelo Configuration Manager, você pode implantar o sistema operacional e outros aplicativos em vários dispositivos de destino.

Use a abordagem ilustrada abaixo para orientá-lo na configuração do Configuration Manager e personalize os exemplos de pacotes e scripts fornecidos nesta orientação, conforme necessário para a sua organização.

![Processo de implantação de salas do Microsoft Teams usando o Configuration Manager](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> Esta solução foi testada apenas com implantações baseadas em Surface pro. Siga as diretrizes do fabricante para configurações que não se baseiam no Surface pro.

## <a name="validate-prerequisites"></a>Validar pré-requisitos

Para implantar salas do Microsoft Teams com o Configuration Manager, verifique se você atende aos seguintes pré-requisitos e requisitos.

### <a name="microsoft-endpoint-configuration-manager-requirements"></a>Requisitos do Gerenciador de configuração do Microsoft Endpoint

-   A versão do Microsoft Endpoint Configuration Manager deve ser pelo menos 1706 ou superior. Recomendamos usar o 1710 ou posterior. Consulte o [suporte do Windows 10 no Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) para saber mais sobre as versões do Windows 10 compatíveis com o Configuration Manager.

-   É preciso instalar uma versão com suporte do kit de avaliação e implantação do Windows (ADK) para Windows 10. Veja as versões do [Windows 10 ADK](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) que você pode usar com versões diferentes do Configuration Manager e certifique-se de que sua implantação inclui a versão correta.

-   Os servidores de sistema de site devem ter sido atribuídos à função de ponto de distribuição, e as imagens de inicialização devem ser habilitadas para [suporte a PXE (ambiente de execução Preboot)](https://docs.microsoft.com/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) para habilitar implantações iniciadas pela rede. Se o suporte a PXE não estiver habilitado, você poderá usar [mídia inicializável](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) para suas implantações.

-   Uma conta de acesso à rede deve ser configurada para dar suporte a novos cenários de implantação de computador (bare metal). Para saber mais sobre a configuração de uma conta de acesso à rede, consulte [contas usadas no Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).

-   Recomendamos que você habilite o [suporte ao multicast](https://docs.microsoft.com/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), se provavelmente você vai implantar a mesma imagem de salas do Microsoft Teams em várias unidades ao mesmo tempo.

### <a name="networking-requirements"></a>Requisitos de rede

-   Sua rede deve ter um servidor DHCP (protocolo de configuração dinâmica de hosts), configurado para distribuição automática de endereços IP para as sub-redes nas quais as unidades de sala do Microsoft Teams serão implantadas.

    > [!NOTE]
    > A duração da concessão DHCP deve ser definida como um valor maior que a duração da implantação da imagem. Caso contrário, a implantação poderá falhar.

-   Sua rede, incluindo opções e LANs virtuais (VLANs), devem ser configuradas para dar suporte ao PXE. Consulte o fornecedor da sua rede para obter mais informações sobre o auxiliar de IP e a configuração PXE. Você também pode usar [mídia inicializável](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) para suas implantações, se o suporte a PXE não estiver habilitado.

    > [!NOTE]
    > Para dispositivos Surface pro, inicializar a partir da rede (inicialização PXE) só tem suporte quando você usa um adaptador Ethernet ou uma docking Station da Microsoft. Adaptadores Ethernet de terceiros não dão suporte à inicialização PXE com Surface pro. Consulte [adaptadores Ethernet e implantação de superfície](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) para obter mais informações.

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a>Configurar o Microsoft Endpoint Configuration Manager para implantação do sistema operacional

Este artigo pressupõe que você já tenha uma implantação íntegra do Configuration Manager e não detalha todas as etapas necessárias para implantar e configurar o Configuration Manager do zero. A [documentação e as diretrizes de configuração](https://docs.microsoft.com/configmgr/) no Gerenciador de configuração do Microsoft Endpoint são um recurso excelente; Recomendamos que você comece com esses recursos se ainda não tiver implantado o Configuration Manager.

Use as instruções a seguir para verificar se os recursos de implantação do sistema operacional (OSD) estão configurados corretamente.

### <a name="validate-and-upgrade-configuration-manager"></a>Validar e atualizar o Configuration Manager

1.  No console do Configuration Manager, acesse **Administration** \> **atualizações e serviços**de administração.

2.  Verifique a compilação instalada e as atualizações aplicáveis que ainda não foram instaladas.

3.  Revise o [suporte para Windows 10 no Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); Se precisar atualizar a implantação, selecione a atualização que você deseja instalar e, em seguida, selecione **baixar**.

4.  Após a conclusão do download, selecione a atualização e, em seguida, selecione **instalar pacote de atualização**.

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a>Configurar pontos de distribuição para dar suporte a PXE e multicast

1.  No console do Configuration Manager, vá para os **pontos de distribuição**de **Administração** \> .

2.  Selecione o servidor de ponto de distribuição que servirá a implantação de salas do Microsoft Teams e selecione **Propriedades**.

3.  Selecione a guia **PXE** e verifique se as seguintes configurações estão habilitadas:
    -   Habilitar o suporte a PXE para clientes
    -   Permitir que este ponto de distribuição responda a solicitações PXE recebidas
    -   Habilitar o suporte a computador desconhecido

4.  *Opcional:* Para habilitar o suporte ao multicast, selecione a guia **multicast** e verifique se as seguintes configurações estão habilitadas:
    -   Habilitar a multicast para enviar dados simultaneamente para vários clientes
    -   Configurar o intervalo de portas UDP de acordo com a recomendação de sua equipe de rede

### <a name="configure-the-network-access-account"></a>Configurar a conta de acesso à rede

1.  No console do Configuration Manager, vá para **sites**de **configuração** \> de site de **Administração** \> e selecione o site.

2.  No grupo **configurações** , selecione **Configurar** \> **distribuição de software**dos componentes do site.

3.  Selecione a guia **conta de acesso à rede** . configurar uma ou mais contas e, em seguida, selecione **OK**.

> [!NOTE]
> As contas não precisam de direitos especiais, exceto para o direito **acesso a este computador pela rede** no servidor de ponto de distribuição. Uma conta de usuário de domínio genérico será apropriada. Para obter mais informações, consulte [contas usadas no Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).

### <a name="configure-a-boot-image"></a>Configurar uma imagem de inicialização

1.  No console do Configuration Manager, vá para **imagens de inicialização**do **sistema** \> operacional da **biblioteca** \> de software.

2.  Selecione **imagem de inicialização (x64)** e, em seguida, selecione **Propriedades**.

3.  Selecione a guia **fonte de dados** e habilite **implantar esta imagem de inicialização do ponto de distribuição habilitado para PXE**.

4.  Selecione a guia **componentes opcionais** para instalar componentes obrigatórios:

    1.  Selecione o ícone estrela e procure por **HTML (WinPE-HTA)**

    2.  Selecione **OK** para adicionar suporte a aplicativo HTML à imagem de inicialização.

5.  *Opcional:* Para personalizar a experiência de implantação, selecione a guia **personalização** .
    -   Habilite o **suporte a comandos (somente teste)** se você quiser ter acesso a um prompt de comando durante a implantação. Quando essa opção estiver habilitada, você poderá iniciar um prompt de comando selecionando **F8** a qualquer momento durante a implantação.
    -   Você também pode especificar uma imagem de tela de fundo personalizada a ser exibida durante a implantação. Para definir uma imagem, habilite **especificar o arquivo de imagem de tela de fundo personalizada (caminho UNC** e selecione seu plano de fundo.

6.  Quando for solicitado, selecione **Sim** e distribua a imagem de inicialização atualizada para seus pontos de distribuição.

Para obter mais informações, consulte [gerenciar imagens de inicialização com o Configuration Manager](https://docs.microsoft.com/configmgr/osd/get-started/manage-boot-images).

> [!NOTE]
> Você pode criar uma mídia USB inicializável para iniciar implantações baseadas em sequência de tarefas do Configuration Manager em ambientes com suporte a PXE. A mídia inicializável contém apenas a imagem de inicialização, os comandos prestart opcionais e os arquivos necessários e os binários do Configuration Manager para dar suporte à inicialização no Windows PE e à conexão com o Configuration Manager para o restante do processo de implantação. Para obter mais informações, consulte [criar mídia inicializável](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).

## <a name="create-configuration-manager-packages"></a>Criar pacotes do Configuration Manager

> [!IMPORTANT]
> A versão do sistema operacional necessária para cada versão do instalador do SRS muda a cada lançamento do MSI. Para determinar a melhor versão do sistema operacional para um determinado MSI, execute o script de configuração do console uma vez. Para saber mais, consulte [implantar salas do Microsoft Teams usando o Gerenciador de configuração do Microsoft Endpoint](rooms-scale.md).

O Configuration Manager requer um número de pacotes para implantar e configurar as unidades de salas do Microsoft Teams.

Você precisa criar e configurar os seguintes pacotes e, em seguida, distribuí-los aos sistemas de site do Configuration Manager que receberam a função de servidor de ponto de distribuição.

| **Nome do pacote**                     | **Tipo**               | **Descrição**                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| SRS v2-pacote de aplicativo SRS     | Pacote de software       | Pacote para o kit de implantação de salas do Microsoft Teams                                      |
| SRS v2-pacote Sysprep             | Pacote de software       | Pacote para o arquivo Unattended. xml personalizado para configurar as unidades de salas do Microsoft Teams            |
| Pacote SRS v2-Set-SRSComputerName | Pacote de software       | Pacote para o aplicativo HTML (HTA) atribuir um nome de computador durante a implantação    |
| SRS v2-configurar a configuração do SRS         | Pacote de software       | Pacote para configurar a implantação do aplicativo salas do Microsoft Teams                          |
| SRS v2-pacote de atualizações do so          | Pacote de software       | Pacote para implantar atualizações obrigatórias do sistema operacional                                      |
| SRS v2-pacote de certificado raiz    | Pacote de software       | Optional – pacote para implantar o certificado raiz (não obrigatório para unidades unidas pelo domínio)  |
| SRS v2-pacote do Microsoft Monitoring Agent | Pacote de software       | Optional-pacote para implantar e configurar o agente do Microsoft Operations Management Suite|
| Pacote em segundo plano do SRS v2-WinPE    | Pacote de software       | Pacote para a imagem de tela de fundo personalizada a ser usada com imagens de inicialização                           |
| Windows 10 Enterprise                | Imagem do sistema operacional | Pacote para o arquivo de instalação do sistema operacional (install. wim)                          |
| Surface Pro                          | Pacote de driver         | Pacote para drivers de dispositivo e firmware para Microsoft Surface pro                     |
| Surface Pro 4                        | Pacote de driver         | Pacote para drivers de dispositivo e firmware para Microsoft Surface Pro 4                   |

Para obter mais informações, consulte [pacotes e programas no Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).

### <a name="create-folders-for-the-package-source-files"></a>Criar pastas para os arquivos de origem do pacote

O Configuration Manager requer que os arquivos de origem do pacote sejam organizados em uma estrutura de pastas específica quando são criados pela primeira vez e quando são atualizados.

Crie a seguinte estrutura de pastas no site de administração central do Gerenciador de ponto de extremidade do Microsoft ou no site primário ou em um compartilhamento de servidor que você está usando para hospedar arquivos de origem do pacote:

-   SRS v2-pacote do Microsoft Monitoring Agent
-   SRS v2-pacote de atualizações do so
-   SRS v2-pacote de certificado raiz
-   Pacote SRS v2-Set-SRSComputerName
-   SRS v2-pacote de aplicativo SRS
-   SRS v2-configurar a configuração do SRS
-   SRS v2-pacote Sysprep
-   Drivers
    -   Surface Pro
    -   Surface Pro 4
-   Sistemas operacionais
    -   Windows 10 Enterprise

> [!TIP]
> Você também pode [baixar](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) e usar o arquivo zip que inclui a estrutura de pastas para os pacotes, os scripts que você precisa usar e o modelo sequência de tarefas, que você precisa importar.

### <a name="create-the-monitoring-agent-package"></a>Criar o pacote do agente de monitoramento

1. Baixe o agente de monitoramento <https://go.microsoft.com/fwlink/?LinkId=828603>de.

2. Extraia o pacote para o **SRS v2-pasta do pacote do Microsoft Monitoring Agent** abrindo uma janela do prompt de comando e digitando **MMASetup-AMD64. exe/c:** no prompt de comando.

3. No console do Configuration Manager, vá para **pacotes**de **Gerenciamento** \> de aplicativos da **biblioteca** \> de software e selecione **criar pacote**.

4. Insira as seguintes informações para criar o pacote:

   - Nome<strong>: SRS v2-pacote do Microsoft Monitoring Agent</strong>

   - Fabricante<strong>: Microsoft Corporation</strong>

   - Versão<strong>: 8.1.11081.0</strong> (Insira a versão do arquivo de instalação baixado)

   - Marque a caixa de seleção **Este pacote contém arquivos de origem** , digite o caminho para a pasta **SRS v2-Microsoft Monitoring Agent** e selecione **Avançar**.

5. Selecione não **criar um programa**e, em seguida, selecione **Avançar**.

6. Examine a página **confirmar as configurações** e, em seguida, selecione **Avançar**.

7. Selecione **fechar**.

### <a name="create-the-operating-system-updates-package"></a>Criar o pacote de atualizações do sistema operacional

1. Na pasta do **pacote atualizações do SRS v2-so** , crie um novo script do PowerShell chamado **install-SRSv2-os-updates. ps1**.

2. Copie o script a seguir para o script **install-SRSv2-os-updates. ps1** . Você também pode baixar o script Install-SRSv2-OS-Updates. ps1 [aqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).
   ```
   # Install-SRSv2-OS-Updates.ps1
   $strPath = split-path -parent $MyInvocation.MyCommand.Definition
   $total = gci $strPath *.msu | measure | Select-Object -expand Count
   $i = 0
   gci $strPath *.msu | ForEach-Object {
     $i++
     WUSA ""$_.FullName /quiet /norestart""
     Write-Progress -activity "Applying Mandatory Updates" -status "Installing
     $_ .. $i of $total" -percentComplete (($i / $total) * 100)
     Wait-Process -name wusa
   }
   ```
3. Baixe os pacotes obrigatórios do Windows Update na mesma pasta.
   > [!NOTE]
   > No momento em que este artigo foi publicado, apenas [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) era necessário. Marque [configurar um console de salas do Microsoft Teams](console.md)para ver se outras atualizações são necessárias.

4. No console do Configuration Manager, vá para **pacotes**de **Gerenciamento** \> de aplicativos da **biblioteca** \> de software e selecione **criar pacote**.

5. Insira as seguintes informações para criar o pacote:
   -   Nome: **SRS v2 – pacote de atualizações do so**
   -   Fabricante: **Microsoft Corporation**
   -   Versão: **1.0.0**
   -   Marque a caixa de seleção **Este pacote contém arquivos de origem** , digite o caminho para a pasta do **pacote de atualizações do SRS v2-os** e selecione **Avançar**.

6. Selecione não **criar um programa**e, em seguida, selecione **Avançar**.

7. Examine a página **confirmar as configurações** e, em seguida, selecione **Avançar**.

8. Selecione **fechar**.

### <a name="create-the-root-certificate-package-optional"></a>Criar o pacote de certificado raiz (opcional)

Você cria esse pacote para distribuir o certificado raiz para dispositivos que não ingressam em um domínio do Active Directory. Crie este pacote somente se ambas as condições a seguir forem aplicáveis:
-   Sua implantação inclui o Lync local ou o Skype for Business Server.
-   As unidades de salas do Microsoft Teams são configuradas para funcionar em um grupo de trabalho em vez de um membro do domínio.

1.  Copie o certificado raiz para a pasta **SRS v2 – pacote de certificado raiz** .

2.  No console do Configuration Manager, vá para **pacotes**de **Gerenciamento** \> de aplicativos da **biblioteca** \> de software e selecione **criar pacote**.

3.  Insira as seguintes informações para criar o pacote:
    -   Nome: **SRS v2 – pacote de certificado raiz**
    -   Fabricante: *o nome da sua organização*
    -   Versão: **1.0.0**
    -   Marque a caixa de seleção **Este pacote contém arquivos de origem** , digite o caminho para a pasta **SRS v2 – pacote de certificado raiz** e selecione **Avançar**.

4.  Selecione não **criar um programa**e, em seguida, selecione **Avançar**.

5.  Examine a página **confirmar as configurações** e, em seguida, selecione **Avançar**.

6.  Selecione **fechar**.

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a>Criar o pacote do kit de implantação de salas do Microsoft Teams

1.  Baixe a versão mais recente <https://go.microsoft.com/fwlink/?linkid=851168>do **Kit de implantação de salas do Microsoft Teams** e instale-a em uma estação de trabalho.

2.  Copie o conteúdo de **C:\\arquivos de programas (x86\\) kit de implantação do sistema de sala do Skype** para a pasta do **pacote de aplicativos SRS v2-SRS** .

3.  No console do Configuration Manager, vá para **pacotes**de **Gerenciamento** \> de aplicativos da **biblioteca** \> de software e selecione **criar pacote**.

4.  Insira as seguintes informações para criar o pacote:
    -   Nome: **SRS v2 – pacote do aplicativo SRS**
    -   Fabricante: **Microsoft Corporation**
    -   Versão: **3.1.104.0** (Insira a versão do arquivo de instalação baixado)
    -   Marque a caixa de seleção **Este pacote contém arquivos de origem** , digite o caminho para a pasta do **pacote de aplicativos SRS v2 – SRS** e selecione **Avançar**.
5.  Selecione não **criar um programa**e, em seguida, selecione **Avançar**.

6.  Examine a página **confirmar as configurações** e, em seguida, selecione **Avançar**.

7.  Selecione **fechar**.

### <a name="create-the-computer-name-assignment-package"></a>Criar o pacote de atribuição de nomes de computador

1.  Na pasta do **pacote SRS v2-Set-SRSComputerName** , crie um novo aplicativo HTML chamado **set-SRSComputerName. hta** .

2.  Copie o seguinte script para o arquivo **set-SRSComputerName. hta** . Você também pode baixar o arquivo Set-SRSComputerName. hta [aqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).
    ```HTML
    <!DOCTYPE HTML>
    <html>
    <head>
    <title>Set SRS Computer Name</title>
    <HTA:APPLICATION
      APPLICATIONNAME="Set SRS Computer Name"
      ID="SetSRSComputerName"
      VERSION="1.0"
      SCROLL="no"
      SINGLEINSTANCE="yes"
      WINDOWSTATE="maximize"
      MaximizeButton="no"
      MinimizeButton="no"
      SysMenu="no"
      ShowInTaskbar="no"
      Caption="no"
      />
    <style type="text/css">
    body {
        background-color: #fdfeff;
        color: darkblue;
        font-family: Calibri;
        font-size: 12pt;
        margin: 4em 3em;
    }
    </style>
    </head>
    <script language="VBScript">
    Public strNewComputerName
    Sub GenerateComputerName()
        strComputer = "."
        Set objWMIService = GetObject("winmgmts:\\" & strComputer & "\root\cimv2")
        Set colItems = objWMIService.ExecQuery("Select * from Win32_BIOS",,48)
        For Each objItem in colItems
            strSerialNumber = objItem.SerialNumber
        Next
        strNewComputerName = "SRS-"  & right(replace(strSerialNumber, "-","") ,10)
        TextArea1.innerHTML = "The serial number of the device: " & strSerialNumber
        strHTMLText = strHTMLText & "<br> Computer name to be assigned: <font color = red>" & strNewComputerName & "</font>"
        strHTMLText = strHTMLText & "<br><br> Click Accept to use this as the computer name and continue deployment, or Change to set a new name."
        strHTMLText = strHTMLText & "<p><input type=""button"" value=""Accept"" name = ""Accept_Button"" onclick=""SetComputerName"" />"
        strHTMLText = strHTMLText & " <input type=""button"" value=""Change"" name = ""Change_Button"" onclick=""ChangeComputerName"" />"
        TextArea2.innerHTML = strHTMLText
    End Sub

    Sub SetComputerName()
        dim result
        result = MsgBox("Computer Name to be assigned: " & strNewComputerName &vbcrlf & "Are you sure you want to continue?", 36)
        If (result = vbYes) then
            SET env = CreateObject("Microsoft.SMS.TSEnvironment")
            env("OSDComputerName") = strNewComputerName
            self.close
        elseif (result = vbNo) then
            Window_OnLoad
        End If
    End Sub

    Sub UpdateComputerName()
        strNewComputerName = newcomputername.value
        if len(trim(strNewComputerName)) = 0 then
            MsgBox "Computer name cannot be empty." &vbcrlf & "Update and try again.",16
            exit sub
        end if
        SetComputerName
    End Sub

    Sub ChangeComputerName()
        TextArea2.innerHTML = "<p>Type the new computer name and click Accept:  <input type=""text"" name=""newcomputername"" value =" & strNewComputerName & " />"
        TextArea2.innerHTML = TextArea2.innerHTML & "<br><input type=""button"" value=""Update"" name = ""Update_Button"" onclick=""UpdateComputerName"" />"
    End Sub

    Sub Window_OnLoad
        Set oTSProgressUI = CreateObject("Microsoft.SMS.TsProgressUI")
        oTSProgressUI.CloseProgressDialog
        GenerateComputerName
    End Sub
    </script>

    <body>
    <span id = "TextArea1"></span>
    <span id = "TextArea2">
    </span>
    </body>
    </html>

    ```
3.  No console do Configuration Manager, vá para **pacotes**de **Gerenciamento** \> de aplicativos da **biblioteca** \> de software e selecione **criar pacote**.

4.  Insira as seguintes informações para criar o pacote:

    -   Nome: **pacote do set-SRSComputerName do SRS v2**

    -   Fabricante: **Microsoft Corporation**

    -   Versão: **1.0.0**

    -   Marque a caixa de seleção **Este pacote contém arquivos de origem** , insira o caminho para a pasta do **pacote SRS v2-Set-SRSComputerName** e selecione **Avançar**.

5.  Selecione não **criar um programa**e, em seguida, selecione **Avançar**.

6.  Examine a página **confirmar as configurações** e, em seguida, selecione **Avançar**.

7.  Selecione **fechar**.

### <a name="create-the-sysprep-package"></a>Criar o pacote Sysprep

1. Na pasta **SRS v2 – pacote Sysprep** , crie um novo arquivo XML denominado **Unattend. xml** .

2. Copie o seguinte texto para o arquivo **Unattend. xml** . Você também pode baixar o arquivo Unattend. XML [aqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).
   ```XML
   <?xml version="1.0" encoding="utf-8"?>
   <unattend xmlns="urn:schemas-microsoft-com:unattend">
   <settings pass="specialize">
       <component name="Microsoft-Windows-Embedded-BootExp" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <DisableBootMenu>1</DisableBootMenu>
           <DisplayDisabled>1</DisplayDisabled>
       </component>
       <component name="Microsoft-Windows-powercpl" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <PreferredPlan>8c5e7fda-e8bf-4a96-9a85-a6e23a8c635c</PreferredPlan>
       </component>
   </settings>
   <settings pass="oobeSystem">
       <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <OOBE>
               <HideEULAPage>true</HideEULAPage>
               <HideLocalAccountScreen>true</HideLocalAccountScreen>
               <HideOEMRegistrationScreen>true</HideOEMRegistrationScreen>
               <HideOnlineAccountScreens>true</HideOnlineAccountScreens>
               <HideWirelessSetupInOOBE>true</HideWirelessSetupInOOBE>
               <SkipMachineOOBE>true</SkipMachineOOBE>
               <SkipUserOOBE>true</SkipUserOOBE>
               <ProtectYourPC>1</ProtectYourPC>
           </OOBE>
           <AutoLogon>
               <Enabled>true</Enabled>
               <Username>Skype</Username>
               <Password>
                   <Value>UABhAHMAcwB3AG8AcgBkAA==</Value>
                   <PlainText>false</PlainText>
               </Password>
           </AutoLogon>
           <UserAccounts>
               <LocalAccounts>
                   <LocalAccount wcm:action="add">
                       <Password>
                           <Value>cwBmAGIAUABhAHMAcwB3AG8AcgBkAA==</Value>
                           <PlainText>false</PlainText>
                       </Password>
                       <Name>Admin</Name>
                       <Group>Administrators</Group>
                       <DisplayName>Administrator</DisplayName>
                       <Description>Administrator</Description>
                   </LocalAccount>
               </LocalAccounts>
           </UserAccounts>
       </component>
   </settings>
   <cpi:offlineImage cpi:source="wim:h:/install.wim#Windows 10 Enterprise" xmlns:cpi="urn:schemas-microsoft-com:cpi" />
   </unattend>
   ```
3. No console do Configuration Manager, vá para **pacotes**de **Gerenciamento** \> de aplicativos da **biblioteca** \> de software e selecione **criar pacote**.

4. Insira as seguintes informações para criar o pacote:
   -   Nome: **SRS v2-pacote Sysprep**
   -   Fabricante: **Microsoft Corporation**
   -   Versão: **1.0.0**
   -   Marque a caixa de seleção **Este pacote contém arquivos de origem** , digite o caminho para a pasta **SRS v2 – pacote Sysprep** e, em seguida, selecione **Avançar**.
5. Selecione não **criar um programa**e, em seguida, selecione **Avançar**.

6. Examine a página **confirmar as configurações** e, em seguida, selecione **Avançar**.

7. Selecione **fechar**.

### <a name="create-the-windows-10-enterprise-package"></a>Criar o pacote do Windows 10 Enterprise

1.  Obtenha uma mídia do Windows 10 Enterprise x64 e copie o arquivo **install. wim** para a pasta **sistemas\\operacionais Windows 10 Enterprise** .

2.  No console do Configuration Manager, vá para **imagens do sistema**operacional dos **sistemas** \> operacionais da **biblioteca** \> de software e selecione **Adicionar imagem do sistema operacional**.

3.  Especifique o caminho para o arquivo **install. wim** que você acabou de copiar e, em seguida, selecione **Avançar**.

4.  Atualize o campo **versão** para corresponder ao número da compilação da imagem do Windows 10 Enterprise e selecione **Avançar**.

5.  Examine a página **detalhes** e, em seguida, selecione **Avançar**.

6.  Selecione **fechar**.

Para obter mais informações, consulte [gerenciar imagens do sistema operacional com o Configuration Manager](https://docs.microsoft.com/configmgr/osd/get-started/manage-operating-system-images).

### <a name="create-surface-pro-device-driver-packages"></a>Criar pacotes de driver de dispositivo Surface pro

As salas do Microsoft Teams são compatíveis com o Surface pro e o Surface Pro 4. Você precisa criar um pacote de driver para cada modelo de Surface pro que você tem em seu ambiente.

> [!IMPORTANT]
> Os drivers devem ser compatíveis com o Windows 10 Enterprise Build e a versão do kit de implantação de salas do Microsoft Teams. Para obter mais informações, consulte [baixar o firmware e os drivers mais recentes para os dispositivos Surface](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) e [configurar um console](console.md).

1.  Baixe os drivers e firmware mais recentes.
    -   Para Surface pro:<https://www.microsoft.com/download/details.aspx?id=55484>
    -   Para Surface Pro 4:<https://www.microsoft.com/download/details.aspx?id=49498>

2.  Extraia o driver e firmware baixados. Abra uma janela do prompt de comando e, no prompt de comando, insira um dos seguintes comandos:
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  No console do Configuration Manager, vá para **drivers**de **sistemas** \> operacionais da **biblioteca** \> de software e selecione **Importar Driver**.

4.  Selecione **importar todos os drivers no seguinte caminho de rede (UNC)**, selecione a pasta de origem (por exemplo,\\C\\:\\_Sources drivers Surface pro) e, em seguida, selecione **Avançar**.

5.  Na página **especificar os detalhes da página de drivers importados** , selecione todos os drivers listados e, em seguida, selecione **habilitar esses drivers e permitir que os computadores os instalem**.

6.  Selecione **categorias**, crie uma nova categoria que corresponda ao modelo de superfície, selecione **OK**e, em seguida, selecione **Avançar**.

7.  Selecione **novo pacote**.

8.  Especifique o nome do pacote que corresponde ao modelo do Surface pro, insira um caminho de pasta para armazenar os arquivos do pacote de driver em, selecione **OK**e, em seguida, selecione **Avançar**.

9.  Na página de **imagens de inicialização** , certifique-se de que nenhuma imagem de inicialização esteja selecionada e selecione **Avançar**.

10. Selecione **fechar**.

11. Vá para **drivers**de **sistemas** \> operacionais da **biblioteca** \> de software, selecione pasta ** \> criar pasta**e insira um nome de pasta que corresponda ao modelo do Surface pro para o qual você acabou de importar os drivers.

12. Mova todos os drivers importados para a pasta recém criada para facilitar a navegação e a operação.

> [!NOTE]
> Repita as mesmas etapas para outros modelos de Surface pro que você possa ter. Para obter mais informações, consulte [gerenciar drivers no Configuration Manager](https://docs.microsoft.com/configmgr/osd/get-started/manage-drivers).

### <a name="create-microsoft-teams-rooms-configuration-package"></a>Criar pacote de configuração de salas do Microsoft Teams

1.  No console do Configuration Manager, vá para **pacotes**de **Gerenciamento** \> de aplicativos da **biblioteca** \> de software e selecione **criar pacote**.

2.  Insira as seguintes informações para criar o pacote:

    -   Nome: **SRS v2-configurar o pacote de configuração do SRS**

    -   Fabricante: **Microsoft Corporation**

    -   Versão: **1.0.0**

    -   Marque a caixa de seleção **Este pacote contém arquivos de origem** , insira o caminho para a pasta **SRS v2-configure SRS setup** e selecione **Avançar**.

3.  Selecione não **criar um programa**e, em seguida, selecione **Avançar**.

4.  Examine a página **confirmar as configurações** e, em seguida, selecione **Avançar**.

5.  Selecione **fechar**.



## <a name="distribute-configuration-manager-packages"></a>Distribuir pacotes do Configuration Manager

Todos os pacotes devem ser distribuídos para os servidores que foram atribuídos à função de ponto de distribuição na hierarquia do Configuration Manager. Siga as instruções abaixo para iniciar a distribuição de pacote.

1.  Distribuir pacotes de software.

    1.  No console do Configuration Manager, vá para **pacotes**de **Gerenciamento** \> de aplicativos da **biblioteca** \> de software. Selecione todos os pacotes de software que você deseja distribuir e, em seguida, selecione **distribuir conteúdo**.

    2.  Examine a lista de pacotes e selecione **Avançar**.

    3.  Adicione todos os servidores de ponto de distribuição (ou grupos de pontos de distribuição, dependendo da sua hierarquia do Configuration Manager) à lista e, em seguida, selecione **Avançar**.

    4.  Selecione **Avançar**e, em seguida, selecione **fechar**.

2.  Distribuir pacotes de driver.

    1.  No console do Configuration Manager, vá para **pacotes de driver**de **sistemas** \> operacionais de **biblioteca** \> de software. Selecione todos os pacotes de driver que você deseja distribuir e, em seguida, selecione **distribuir conteúdo**.

    2.  Examine a lista de pacotes e selecione **Avançar**.

    3.  Adicione todos os servidores de ponto de distribuição (ou grupos de pontos de distribuição, dependendo da sua hierarquia do Configuration Manager) à lista e, em seguida, selecione **Avançar**.

    4.  Selecione **Avançar**e, em seguida, selecione **fechar**.

3.  Distribuir pacotes do sistema operacional.

    1.  No console do Configuration Manager, vá para **imagens do sistema operacional**dos **sistemas** \> operacionais da **biblioteca** \> de software. Selecione todas as imagens do sistema operacional que você deseja distribuir e, em seguida, selecione **distribuir conteúdo**.

    2.  Examine a lista de pacotes e selecione **Avançar**.

    3.  Adicione todos os servidores de ponto de distribuição (ou grupos de pontos de distribuição, dependendo da sua hierarquia do Configuration Manager) à lista e, em seguida, selecione **Avançar**.

    4.  Selecione **Avançar**e, em seguida, selecione **fechar**.

> [!NOTE]
> A distribuição de pacote pode levar algum tempo, dependendo do tamanho do pacote, da hierarquia do Configuration Manager, do número de servidores de ponto de distribuição e da largura de banda disponível na rede.
> 
> Todos os pacotes devem ser distribuídos para que você possa começar a implantar uma unidade de salas do Microsoft Teams.
> 
> Você pode examinar o status da distribuição do pacote no console do Configuration Manager indo **monitorar** \> **Distribution Status** \> **status do conteúdo**do status da distribuição.

## <a name="configuration-manager-task-sequences"></a>Sequências de tarefas do Configuration Manager

Você usa sequências de tarefas com o Configuration Manager para automatizar as etapas para implantar uma imagem do sistema operacional em um computador de destino. Para implantar uma unidade de salas do Microsoft Teams de maneira automatizada, crie uma sequência de tarefas que referencie a imagem de inicialização usada para iniciar o computador de salas de destino do Microsoft Teams, a imagem do sistema operacional do Windows 10 Enterprise que você deseja instalar e qualquer outro conteúdo adicional, como outros aplicativos ou atualizações de software.

### <a name="import-the-sample-task-sequence"></a>Importar a sequência de tarefas de exemplo

Você pode baixar e importar facilmente uma sequência de tarefas de exemplo e personalizá-la para atender às suas necessidades.

1.  [**Baixe**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) a sequência de tarefas de exemplo e copie o arquivo zip baixado para um local compartilhado.
2.  No console do Configuration Manager, vá para **sequências de tarefas**de **sistemas** \> operacionais da **biblioteca** \> de software e selecione **importar sequência de tarefas**.

3.  Selecione **procurar**, vá para o local da pasta compartilhada que você usou na etapa 1, selecione o arquivo **. zip da implantação de salas do Microsoft Teams (en-US)** e, em seguida, selecione **Avançar**.

4.  Defina **ação** para **criar novo**e, em seguida, selecione **Avançar**.

5.  Confirme as configurações e, em seguida, selecione **Avançar**.

6.  Selecione **fechar**.

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a>Valide se os pacotes de referência estão vinculados corretamente a cada etapa de sequência de tarefas.

1. Selecione a sequência de tarefas importada e, em seguida, selecione **Editar**.

    O editor de sequência de tarefas abre e exibe cada etapa sequencial que você precisa para implantar e configurar uma unidade de salas do Microsoft Teams.

2. Percorra cada etapa e conclua as atualizações recomendadas:

   1. **Reinicie no Windows PE**: essa etapa reinicia e inicializa o computador no Windows PXE. Nenhuma alteração é necessária para esta etapa.

   2. **Partition Disk 0 – UEFI**: esta etapa apaga a configuração do disco e cria partições com base nas configurações definidas. Recomendamos que você não faça nenhuma alteração nesta etapa.

   3. **Definir o nome do computador SRS**: esta etapa inclui um aplicativo HTML para fornecer uma interface do usuário para definir um nome de computador para a unidade de salas do Microsoft Teams durante a implantação.
      -  Esta etapa é opcional, mas só poderá ser desabilitada se você quiser gerenciar o nome do computador por meio de um processo alternativo.
      -  Verifique se o pacote **SRS v2-Set-SRSComputerName** está selecionado. Se não estiver, navegue até o pacote e selecione-o.

   4. **Aplicar sistema operacional**: esta etapa especifica a imagem do sistema operacional a ser implantada e o arquivo de resposta do Sysprep autônomo a ser usado.
      -  Verifique se o arquivo de imagem correto do sistema operacional Windows 10 Enterprise está selecionado.
      -  Verifique se o uso de um **arquivo de resposta autônomo ou Sysprep para uma instalação personalizada** está habilitado e se o **pacote SRS v2-Sysprep** está selecionado. Além disso, certifique-se de que o **nome do arquivo** esteja definido como Unattend **. xml**.

   5. **Aplicar configurações do Windows**: esta etapa coleta informações sobre a instalação do Windows.
      -  Forneça informações de licenciamento e registro, incluindo a chave do produto, a senha da conta de administrador local e o fuso horário (dependendo das suas necessidades).

   6. **Aplicar configurações de rede**: esta etapa permite que você especifique um grupo de trabalho ou um nome de domínio e uma unidade organizacional do Active Directory.
      > [!NOTE]
      > Consulte [domínio do sistema de sala da Skype considerações sobre](domain-joining-considerations.md) as ações recomendadas para a implantação de unidades de sala do Microsoft Teams como membros de um domínio do diretório actve.
   7. **Aplicar drivers:** Esta etapa e suas subetapas são usadas para implantar drivers de dispositivo e firmware aplicáveis com base no modelo do Surface pro que você tem. Atualize cada etapa para especificar o pacote de driver apropriado associado a essa implantação.
      -   Cada pacote de driver é configurado para aproveitar os filtros de instrumentação de gerenciamento do Windows (WMI) para implantar drivers relevantes e firmware com base na marca e no modelo do Surface pro.
      -   É altamente recomendável que você não altere a configuração desses drivers, caso contrário, a implantação poderá falhar.

   8. **Configurar o Windows e o Gerenciador de configurações**: esta etapa implanta e configura o cliente do Configuration Manager. Atualize esta etapa para especificar o pacote interno do cliente do Configuration Manager.

   9. **Instalar certificado raiz**: esta etapa distribui o certificado raiz para dispositivos não associados ao domínio e, portanto, é opcional e desabilitado por padrão.
      -   Habilite esta etapa se você precisar implantar um certificado raiz nas unidades de salas de Microsoft Teams.
      -   Se você precisar executar esta etapa, verifique se o pacote de **certificado raiz do SRS v2** e **desabilite o redirecionamento do sistema de arquivos de 64** está selecionado.

   10. **Instalar e configurar o agente de monitoramento**: esta etapa instala a versão de 64 bits do agente de monitor do Microsoft Azure e configura o agente para se conectar ao espaço de trabalho de análise de log.
       -   Esta etapa é desativada por padrão. Habilite essa etapa somente se você for usar o agente de monitoramento para monitorar a integridade de suas unidades de sala de Microsoft Teams.
       -   Edite esta etapa e atualize os parâmetros de linha de comando para especificar a **ID do espaço de trabalho** e a chave do espaço de **trabalho**.
       -   Consulte [configurar dispositivos de teste para monitoramento do Azure](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) para obter mais informações sobre como obter a ID do espaço de trabalho do Operations Management Suite e a chave primária.
       -   Verifique se o **pacote SRS v2 – Microsoft Monitoring Agent** e **desabilite o redirecionamento do sistema de arquivos de 64-bit** está selecionado.
       -   Para obter mais informações sobre como monitorar a integridade da implantação de salas do Microsoft Teams, consulte planejar o gerenciamento de salas do Microsoft [Teams com o Azure monitor](azure-monitor-plan.md), [implantar o gerenciamento de salas do Microsoft Teams com o Azure monitor](azure-monitor-deploy.md) e [gerenciar dispositivos de salas do Microsoft Teams com o Azure monitor](azure-monitor-manage.md)

   11. **Copiar os arquivos de configuração do SRS v2**: esta etapa copia os arquivos de configuração e configuração necessários do kit de implantação de salas do Microsoft Teams para o disco rígido local. Nenhuma personalização é necessária para esta etapa.
       -   Verifique se o **pacote do aplicativo SRS v2 – SRS** e **desabilite o redirecionamento do sistema de arquivos do 64-bit** está selecionado.

   12. **Install-SRSv2-os-so-updates**: esta etapa implanta todas as atualizações obrigatórias do sistema operacional necessárias para a implantação de salas do Microsoft Teams. Siga este procedimento:
       -   Marque [configurar um console de salas do Microsoft Teams](console.md) para ver quais atualizações são necessárias.
       -   Verifique se o **pacote de atualizações do SRS v2 – so** inclui todas as atualizações necessárias.
       -   Verifique se o **SRS v2 – pacote de atualizações do so** está selecionado.
       -   Verifique se a política de execução do PowerShell está definida como **ignorar**.

   13. **Reiniciar computador**: esta etapa reinicializa o computador após a instalação das atualizações obrigatórias do sistema operacional. Nenhuma personalização é necessária para esta etapa.

   14. **Configurar componentes do Windows**: esta etapa configura os recursos necessários do Windows. Nenhuma personalização é necessária para esta etapa.

   15. **Reiniciar computador**: esta etapa reinicializa o computador após a configuração dos recursos do Windows. Nenhuma personalização é necessária para esta etapa.

   16. **Adicionar usuário local do Skype**: esta etapa cria a conta do Skype local usada para entrar automaticamente no Windows e iniciar o aplicativo salas do Microsoft Teams. Esta etapa não tem nenhum pacote de software associado a ele, e nenhuma personalização é necessária para ele.

   17. **Configurar e configurar o aplicativo SRS**: esta etapa configura a instalação do aplicativo salas do Microsoft Teams para a próxima inicialização do sistema operacional.
       -   Verifique se o **SRS v2 – configurar o pacote de configuração do SRS** e **desativar o redirecionamento do sistema de arquivos de 64 bits** está selecionado.

> [!IMPORTANT]
> É muito importante que as etapas da sequência de tarefas devem estar na ordem fornecida. Modificar a ordem das etapas ou configurar etapas adicionais pode interromper a implantação.
>
> **Configurar e configurar o aplicativo SRS** a etapa deve ser a última etapa na sequência de tarefas, caso contrário, a implantação poderá falhar.

### <a name="create-deployment-for-the-task-sequence"></a>Criar implantação para a sequência de tarefas

1. Selecione a sequência de tarefas e, em seguida, selecione **implantar**.

2. Selecione **procurar** para selecionar a coleção de destino para implantação.

3. Selecione **todos os computadores desconhecidos** e, em seguida, selecione **OK**.

4. Selecione **Avançar**.

5. Selecione **disponível** na lista suspensa **finalidade** .

6. Selecione **somente mídia e PXE** na lista **fazer disponível para a lista a seguir** e selecione **Avançar**.
   > [!WARNING]
   > É muito importante que a **finalidade** seja definida como **disponível**. Verifique se a **finalidade** **não** está definida como **obrigatória**. Além disso, certifique-se de selecionar **somente mídia e PXE** na opção disponibilizar **para o seguinte**.
   >
   > Configurar esses valores para algo mais pode fazer com que todos os computadores obtenham a imagem de implantação de salas do Microsoft Teams quando inicializados.
7. Não especifique nenhum agendamento e selecione **Avançar**.

8. Não altere nada na seção **experiência do usuário** e selecione **Avançar**.

9. Não altere nada na seção **alertas** e selecione **Avançar**.

10. Não altere nada na seção **pontos de distribuição** e selecione **Avançar**.

11. Confirme as configurações e, em seguida, selecione **Avançar**.

12. Selecione **fechar**.

<a name="validate-and-troubleshoot-the-solution"></a>Validar e solucionar problemas com a solução
--------------------------------------

Depois de concluir as sequências de tarefas do Microsoft Endpoint Configuration Manager, você precisará executar uma execução de teste para validar que a sequência de tarefas pode implantar e configurar unidades de sala de equipe do Microsoft Teams.

1.  Conecte o dispositivo de teste à rede com fio usando um dos adaptadores Ethernet compatíveis ou usando o Dock Dock. Se a funcionalidade de inicialização PXE não tiver sido configurada para o seu ambiente, você poderá usar a imagem de inicialização na unidade flash USB [que você criou anteriormente](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media) para inicializar a partir do USB e conectar-se ao Configuration Manager.

2.  Acesse o firmware e inicie a inicialização PXE:

    1.  Verifique se o dispositivo de Surface está desligado.

    2.  Pressione e mantenha pressionado o botão **aumentar volume** .

    3.  Pressione e libere o botão de **energia** .

    4.  Depois que o dispositivo começar a inicializar, solte o botão **aumentar volume** .

    5.  Selecione **configuração de inicialização**.

    6.  Siga um destes procedimentos:

        -   Selecione **inicialização PXE**e arraste-o para a parte superior da lista. Você também pode passar o dedo para a esquerda no adaptador de rede para inicializar o dispositivo imediatamente. Isso não afetará a ordem de inicialização.
        -   Selecione a unidade flash USB que contém a mídia de inicialização.

3.  Selecione **sair**e, em seguida, selecione **reiniciar agora**.

4.  Quando solicitado, selecione **Enter** for Network boot Service.

5.  O Windows PE será carregado na memória, e o assistente de sequência de tarefas será iniciado. Selecione **Avançar** para continuar.

6.  Selecione a sequência de tarefas que você importou anteriormente e, em seguida, selecione **Avançar**.

7.  Após a aplicação da configuração do disco, você será solicitado a especificar um nome de computador para o dispositivo. A interface do usuário exibirá um nome de computador recomendado com base no número de série do dispositivo do Surface pro. Você pode aceitar o nome proposto ou especificar um novo. Siga as instruções na tela atribuição de nome do computador. Quando você selecionar **aceitar**, a implantação começará.

8.  O restante do processo de implantação é automático e não solicita mais entrada do usuário.

9.  Depois que a sequência de tarefas de implantação terminar de configurar o dispositivo, você verá a seguinte tela de configuração que solicita que você defina as configurações do aplicativo salas do Microsoft Teams.

    ![Tela inicial de configuração do aplicativo salas do Microsoft Teams](../media/room-systems-scale-image2.png)

10.  Conecte o Surface pro ao console de salas do Microsoft Teams e defina as configurações do aplicativo.

11.  Valide se os recursos listados na [ajuda das salas do Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) estão trabalhando no dispositivo implantado.


Para solucionar uma falha na instalação, verifique o arquivo **SMSTS. log** , que registra todas as etapas executadas em uma sequência de tarefas do Configuration Manager.

O arquivo SMSTS. log está armazenado em um de vários caminhos, dependendo do estágio do processo de compilação. Verifique a tabela a seguir para identificar o caminho para o arquivo SMSTS. log.


| **Fase de implantação**                                                            | **Caminho do log da sequência de tarefas**                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| WinPE, antes do formato do HDD                                                        | X:\\Windows\\temp\\smstslog\\SMSTS. log             |
| WinPE, após o formato do HDD                                                         | C:\\_SMSTaskSequence\\registra\\-\\se Smstslog SMSTS. log    |
| Sistema operacional implantado antes da instalação do agente do Configuration Manager | c:\\_SMSTaskSequence\\registra\\-\\se Smstslog SMSTS. log    |
| Sistema operacional e o agente do Configuration Manager implantado                   | % WINDIR%\\system32\\CCM\\logs\\Smstslog\\SMSTS. log |
| Execução da sequência de tarefas concluída                                                | % WINDIR%\\system32\\CCM\\registra\\SMSTS. log           |

> [!TIP]
> Você pode selecionar **F8** a qualquer momento durante a sequência de tarefas para abrir um console de comando e, em seguida, obter acesso ao arquivo SMSTS. log.

Para solucionar problemas de inicialização PXE, verifique os dois arquivos de log no servidor do Configuration Manager que são específicos para ações PXE:

-   **Pxecontrol. log**, localizado no diretório de logs de instalação do Configuration Manager

-   **Smspxe. log**, localizado no diretório de logs do ponto de gerenciamento do Configuration Manager (MP)

Para obter uma lista completa dos arquivos de log que você pode usar para solucionar problemas com a instalação do Configuration Manager, consulte a [referência do arquivo de log](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/log-files)do Microsoft Endpoint Configuration Manager.
