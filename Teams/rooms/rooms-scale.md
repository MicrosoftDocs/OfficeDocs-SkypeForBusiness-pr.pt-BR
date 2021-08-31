---
title: Implantar Salas do Microsoft Teams usando Microsoft Endpoint Configuration Manager
author: dstrome
ms.author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: Saiba mais sobre como implantar Salas do Microsoft Teams em implantações em grande escala usando Microsoft Endpoint Configuration Manager.
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
ms.openlocfilehash: 27cd37df8516973ddf9fbe6401a1e4c21ce01e0a
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731570"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a>Implantar Salas do Microsoft Teams usando Microsoft Endpoint Configuration Manager

Este artigo fornece todas as informações necessárias para criar suas implantações Salas do Microsoft Teams usando Microsoft Endpoint Configuration Manager.

Com os métodos fáceis de usar fornecidos pelo Configuration Manager, você pode implantar o sistema operacional e outros aplicativos em vários dispositivos de destino.

Use a abordagem ilustrada abaixo para orientá-lo através de sua configuração do Configuration Manager e personalizar os pacotes de exemplo e scripts fornecidos ao longo desta orientação, conforme necessário para sua organização.

![Salas do Microsoft Teams de implantação usando o Configuration Manager.](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> Essa solução só foi testada com implantações Surface Pro baseadas em Surface Pro. Siga as diretrizes do fabricante para configurações que não se baseiam em Surface Pro.

## <a name="validate-prerequisites"></a>Validar pré-requisitos

Para implantar Salas do Microsoft Teams com o Configuration Manager, certifique-se de atender aos seguintes pré-requisitos e requisitos.

### <a name="microsoft-endpoint-configuration-manager-requirements"></a>Microsoft Endpoint Configuration Manager requisitos

-   Microsoft Endpoint Configuration Manager versão deve ter pelo menos 1706 ou mais. Recomendamos usar o 1710 ou posterior. Confira Suporte [para Windows 10 no Configuration Manager](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) para saber mais sobre as versões Windows 10 compatíveis com o Configuration Manager.

-   Uma versão com suporte do Windows Kit de Avaliação e Implantação (ADK) para Windows 10 deve ser instalada. Consulte as versões do [Windows 10 ADK](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) que você pode usar com versões diferentes do Configuration Manager e certifique-se de que sua implantação inclua a versão correta.

-   Os servidores do sistema de site devem ter sido atribuídos à função de ponto de distribuição, e as imagens de inicialização devem estar habilitadas para suporte ao [PXE (ambiente](/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) de execução de pré-inicialização) para habilitar implantações iniciadas na rede. Se o suporte a PXE não estiver habilitado, você poderá usar mídia [inicializável](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) para suas implantações.

-   Uma conta de acesso à rede deve ser configurada para dar suporte a novos cenários de implantação do computador (bare metal). Para saber mais sobre a configuração de uma conta de acesso à rede, consulte [Contas usadas no Configuration Manager](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).

-   Recomendamos que você habilita o suporte a [multicast](/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), se for provável que você implante a mesma imagem Salas do Microsoft Teams em várias unidades ao mesmo tempo.

### <a name="networking-requirements"></a>Requisitos de rede

-   Sua rede deve ter um servidor DHCP (Dynamic Host Configuration Protocol), configurado para distribuição automática de endereço IP para as sub-redes nas quais Salas do Microsoft Teams unidades serão implantadas.

    > [!NOTE]
    > A duração do contrato de locação de DHCP deve ser definida como um valor maior do que a duração da implantação da imagem. Caso contrário, a implantação pode falhar.

-   Sua rede, incluindo comutadores e VLANs virtuais, deve ser configurada para dar suporte a PXE. Consulte seu fornecedor de rede para obter mais informações sobre a configuração do Ip Helper e PXE. Como alternativa, você pode usar mídia [inicializável](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) para suas implantações, se o suporte PXE não estiver habilitado.

    > [!NOTE]
    > Para Surface Pro, a inicialização da rede (inicialização PXE) só é suportada quando você usa um adaptador Ethernet ou uma estação de encaixe da Microsoft. Adaptadores Ethernet de terceiros não suportam inicialização PXE com Surface Pro. Consulte [Adaptadores Ethernet e implantação do Surface](/surface/ethernet-adapters-and-surface-device-deployment) para obter mais informações.

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a>Configurar Microsoft Endpoint Configuration Manager para implantação do sistema operacional

Este artigo supõe que você já tenha uma implantação saudável do Configuration Manager e não detalha todas as etapas necessárias para implantar e configurar o Configuration Manager do zero. A [documentação e as diretrizes de](/configmgr/) configuração sobre o Microsoft Endpoint Configuration Manager é um ótimo recurso; recomendamos que você comece com esses recursos se ainda não tiver implantado o Configuration Manager.

Use as instruções a seguir para verificar se os recursos de implantação do sistema operacional (OSD) estão configurados corretamente.

### <a name="validate-and-upgrade-configuration-manager"></a>Validar e atualizar o Configuration Manager

1.  No console do Configuration Manager, vá para **Atualizações** \> **de Administração e Manutenção.**

2.  Verifique a com build instalada e as atualizações aplicáveis que ainda não foram instaladas.

3.  Revise [o suporte para Windows 10 no Configuration Manager;](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) se você precisar atualizar sua implantação, selecione a atualização que deseja instalar e selecione **Baixar**.

4.  Depois que o download for concluído, selecione a atualização e selecione **Instalar o Pacote de Atualizações.**

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a>Configurar pontos de distribuição para dar suporte a PXE e multicast

1.  No console do Configuration Manager, vá para **Pontos de Distribuição de** \> **Administração**.

2.  Selecione o servidor de ponto de distribuição que atenderá à implantação Salas do Microsoft Teams e selecione **Propriedades**.

3.  Selecione a **guia PXE** e verifique se as seguintes configurações estão habilitadas:
    -   Habilitar o suporte PXE para clientes
    -   Permitir que esse ponto de distribuição responda a solicitações PXE de entrada
    -   Habilitar suporte a computadores desconhecidos

4.  *Opcional:* Para habilitar o suporte a várioscasts, selecione a guia **Multicast** e verifique se as seguintes configurações estão habilitadas:
    -   Habilitar o multicast para enviar dados simultaneamente a vários clientes
    -   Configurar o intervalo de portas UDP de acordo com a recomendação da sua equipe de rede

### <a name="configure-the-network-access-account"></a>Configurar a Conta de Acesso à Rede

1.  No console do Configuration Manager, vá para **Sites** de Configuração do Site de \>  \> Administração e selecione o site.

2.  No grupo **Configurações,** selecione Configurar Distribuição de Software **de** \> **Componentes de Site**.

3.  Selecione a **guia Conta de Acesso à** Rede. Configurar uma ou mais contas e selecione **OK**.

> [!NOTE]
> As contas não precisam de direitos especiais, exceto o **Access this computer** da rede no servidor de ponto de distribuição. Uma conta de usuário de domínio genérico será apropriada. Para obter mais informações, consulte [Contas usadas no Configuration Manager](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).

### <a name="configure-a-boot-image"></a>Configurar uma imagem de inicialização

1.  No console do Configuration Manager, acesse Imagens de **inicialização** do sistema \> **operacional da Biblioteca de** \> Software.

2.  Selecione **Imagem de inicialização (x64)** e selecione **Propriedades**.

3.  Selecione a **guia Fonte de** Dados e habilita a Implantação dessa imagem de inicialização do ponto de distribuição habilitado para **PXE.**

4.  Selecione a **guia Componentes Opcionais** para instalar os componentes necessários:

    1.  Selecione o ícone de estrela e procure **HTML (WinPE-HTA)**

    2.  Selecione **OK** para adicionar suporte a aplicativo HTML à imagem de inicialização.

5.  *Opcional:* Para personalizar a experiência de implantação, selecione a **guia Personalização.**
    -   Habilita o suporte a comandos **(somente teste)** se você quiser ter acesso a um prompt de comando durante a implantação. Quando isso estiver habilitado, você poderá iniciar um prompt de comando selecionando **F8** a qualquer momento durante a implantação.
    -   Você também pode especificar uma imagem de plano de fundo personalizada a ser exibida durante a implantação. Para definir uma imagem, **habilita Especifique o arquivo de imagem de plano** de fundo personalizado (caminho UNC e selecione seu plano de fundo.

6.  Quando solicitado, selecione **Sim e** distribua a imagem de inicialização atualizada para seus pontos de distribuição.

Para obter mais informações, consulte [Gerenciar imagens de inicialização com o Configuration Manager](/configmgr/osd/get-started/manage-boot-images).

> [!NOTE]
> Você pode criar uma mídia USB inicializável para iniciar implantações baseadas em sequência de tarefas do Configuration Manager para ambientes que não têm suporte para PXE. A mídia inicializável contém apenas a imagem de inicialização, comandos de prestart opcionais e seus arquivos necessários e binários do Configuration Manager para dar suporte à inicialização no Windows PE e à conexão com o Configuration Manager para o restante do processo de implantação. Para obter mais informações, consulte [Create bootable media](/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).

## <a name="create-configuration-manager-packages"></a>Criar pacotes do Configuration Manager

> [!IMPORTANT]
> A versão necessária do sistema operacional para cada versão do instalador SRS é modificada a cada versão MSI. Para determinar a melhor versão do sistema operacional para um determinado MSI, execute o script de configuração do console uma vez. Para saber mais, consulte [Deploy Salas do Microsoft Teams using Microsoft Endpoint Configuration Manager](rooms-scale.md).

O Configuration Manager requer vários pacotes para implantar e configurar as unidades Salas do Microsoft Teams de configuração.

Você precisa criar e configurar os seguintes pacotes e distribuí-los para os sistemas de site do Configuration Manager que foram atribuídos à função de servidor de ponto de distribuição.

| **Nome do pacote**                     | **Tipo**               | **Descrição**                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| SRS v2 - Pacote de Aplicativos SRS     | Pacote de software       | Pacote para o Salas do Microsoft Teams de implantação                                      |
| SRS v2 - Pacote Sysprep             | Pacote de software       | Pacote para o Unattended.xml para configurar Salas do Microsoft Teams unidades            |
| SRS v2 - Set-SRSComputerName Pacote | Pacote de software       | Pacote para o aplicativo HTML (HTA) para atribuir um nome de computador durante a implantação    |
| SRS v2 - Configurar a Instalação do SRS         | Pacote de software       | Pacote para configurar a implantação do Salas do Microsoft Teams app                          |
| SRS v2 - Pacote de Atualizações do sistema operacional          | Pacote de software       | Pacote para implantar atualizações obrigatórias do sistema operacional                                      |
| SRS v2 - Pacote de Certificado Raiz    | Pacote de software       | Opcional - Pacote para implantar o certificado raiz (não necessário para unidades ingressadas no domínio)  |
| SRS v2 - Microsoft Monitoring Agent Pacote | Pacote de software       | Opcional - Pacote para implantar e configurar o agente do Microsoft Operations Management Suite|
| SRS v2 - Pacote de Plano de Fundo do WinPE    | Pacote de software       | Pacote para a imagem de plano de fundo personalizada a ser usada com imagens de inicialização                           |
| Windows 10 Enterprise                | Imagem do sistema operacional | Pacote para o arquivo de instalação do sistema operacional (install.wim)                          |
| Surface Pro                          | Pacote driver         | Pacote para drivers de dispositivo e firmware para Microsoft Surface Pro                     |
| Surface Pro 4                        | Pacote driver         | Pacote para drivers de dispositivo e firmware para Microsoft Surface Pro 4                   |

Para obter mais informações, consulte [Pacotes e programas no Configuration Manager](/configmgr/apps/deploy-use/packages-and-programs).

### <a name="create-folders-for-the-package-source-files"></a>Criar pastas para os arquivos de origem do pacote

O Configuration Manager exige que os arquivos de origem do pacote sejam organizados em uma estrutura de pasta específica quando eles são criados pela primeira vez e quando são atualizados.

Crie a seguinte estrutura de pastas no site Microsoft Endpoint Configuration Manager administração central ou site principal ou em um compartilhamento de servidor que você está usando para hospedar arquivos de origem do pacote:

-   SRS v2 - Microsoft Monitoring Agent Pacote
-   SRS v2 - Pacote de Atualizações do sistema operacional
-   SRS v2 - Pacote de Certificado Raiz
-   SRS v2 - Set-SRSComputerName Pacote
-   SRS v2 - Pacote de Aplicativos SRS
-   SRS v2 - Configurar a Instalação do SRS
-   SRS v2 - Pacote Sysprep
-   Drivers
    -   Surface Pro
    -   Surface Pro 4
-   Sistemas Operacionais
    -   Windows 10 Enterprise

> [!TIP]
> Você também pode [baixar](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) e usar o arquivo zip que inclui a estrutura de pastas para os pacotes, os scripts que você precisa usar e o modelo de sequência de tarefas que você precisa importar.

### <a name="create-the-monitoring-agent-package"></a>Criar o pacote do agente de monitoramento

1. Baixe o agente de Monitoramento de <https://go.microsoft.com/fwlink/?LinkId=828603> .

2. Extraia o pacote na pasta **Pacote do SRS v2 - Microsoft Monitoring Agent** abrindo uma janela do Prompt de Comando e inserindoMMASetup-AMD64.exe **/C:** no prompt de comando.

3. No console do Configuration Manager, vá para Pacotes de Gerenciamento de Aplicativos da Biblioteca de **Software** e selecione \>  \>  **Criar Pacote**.

4. Insira as seguintes informações para criar o pacote:

   - Nome<strong>: SRS v2 - Microsoft Monitoring Agent Pacote</strong>

   - Fabricante<strong>: Microsoft Corporation</strong>

   - Versão<strong>: 8.1.11081.0</strong> (insira a versão do arquivo de instalação baixado)

   - Marque a caixa de seleção **Este** pacote contém arquivos de origem, insira o caminho para a pasta **SRS v2 - Microsoft Monitoring Agent Pacote** e selecione **Próximo**.

5. Selecione **Não criar um programa e** selecione **Próximo**.

6. Revise a **página Confirmar as configurações** e selecione **Próximo**.

7. Selecione **Fechar**.

### <a name="create-the-operating-system-updates-package"></a>Criar o pacote de atualizações do sistema operacional

1. Na pasta Pacote de Atualizações do SISTEMA OPERACIONAL do **SRS v2,** crie um novo script do PowerShell chamado **Install-SRSv2-OS-Updates.ps1**.

2. Copie o script abaixo para o **scriptInstall-SRSv2-OS-Updates.ps1** script. Como alternativa, você pode baixar o script Install-SRSv2-OS-Updates.ps1 a [partir daqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).
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
3. Baixe os pacotes Windows Update obrigatórios na mesma pasta.
   > [!NOTE]
   > No momento em que este artigo foi publicado, apenas [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) era necessário. Verifique [Configurar um console Salas do Microsoft Teams](console.md), para ver se outras atualizações são necessárias.

4. No console do Configuration Manager, vá para Pacotes de Gerenciamento de Aplicativos da Biblioteca de **Software** e selecione \>  \>  **Criar Pacote**.

5. Insira as seguintes informações para criar o pacote:
   -   Nome: **SRS v2 – Pacote de atualizações do sistema operacional**
   -   Fabricante: **Microsoft Corporation**
   -   Versão: **1.0.0**
   -   Marque a **caixa de** seleção Este pacote contém arquivos de origem, insira o caminho para a pasta **SrS v2 - Pacote** de Atualizações do sistema operacional e selecione **Próximo**.

6. Selecione **Não criar um programa e** selecione **Próximo**.

7. Revise a **página Confirmar as configurações** e selecione **Próximo**.

8. Selecione **Fechar**.

### <a name="create-the-root-certificate-package-optional"></a>Criar o pacote de certificado raiz (opcional)

Você cria esse pacote para distribuir o certificado raiz para dispositivos que não serão ingressados em um domínio do Active Directory. Crie este pacote somente se as duas condições a seguir se aplicarem:
-   Sua implantação inclui o Lync local ou Skype for Business Server.
-   Salas do Microsoft Teams unidades são configuradas para funcionar em um grupo de trabalho em vez de um membro do domínio.

1.  Copie o certificado raiz para a pasta **SRS v2 – Pacote de Certificado** Raiz.

2.  No console do Configuration Manager, vá para Pacotes de Gerenciamento de Aplicativos da Biblioteca de **Software** e selecione \>  \>  **Criar Pacote**.

3.  Insira as seguintes informações para criar o pacote:
    -   Nome: **SRS v2 – Pacote de Certificado Raiz**
    -   Fabricante: *nome da sua organização*
    -   Versão: **1.0.0**
    -   Marque a caixa de seleção **Este pacote contém** arquivos de origem, insira o caminho para a pasta **SRS v2 – Pacote** de Certificado Raiz e selecione **Próximo**.

4.  Selecione **Não criar um programa e** selecione **Próximo**.

5.  Revise a **página Confirmar as configurações** e selecione **Próximo**.

6.  Selecione **Fechar**.

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a>Criar o pacote Salas do Microsoft Teams kit de implantação

1.  Baixe a versão mais recente do **Salas do Microsoft Teams de implantação** <https://go.microsoft.com/fwlink/?linkid=851168> de , e instale-a em uma estação de trabalho.

2.  Copie o conteúdo de C: Arquivos de **\\ Programa (x86) \\ Skype Kit** de Implantação do Sistema de Sala para a pasta Pacote de Aplicativos **SRS v2 - SRS.**

3.  No console do Configuration Manager, vá para Pacotes de Gerenciamento de Aplicativos da Biblioteca de **Software** e selecione \>  \>  **Criar Pacote**.

4.  Insira as seguintes informações para criar o pacote:
    -   Nome: **SRS v2 – Pacote de Aplicativos SRS**
    -   Fabricante: **Microsoft Corporation**
    -   Versão: **3.1.104.0** (insira a versão do arquivo de instalação baixado)
    -   Marque a **caixa de** seleção Este pacote contém arquivos de origem, insira o caminho para a pasta Pacote de Aplicativos **SRS v2 – SRS** e selecione **Próximo**.
5.  Selecione **Não criar um programa e** selecione **Próximo**.

6.  Revise a **página Confirmar as configurações** e selecione **Próximo**.

7.  Selecione **Fechar**.

### <a name="create-the-computer-name-assignment-package"></a>Criar o pacote de atribuição de nome de computador

1.  Na pasta **Pacote do SRS v2 - Set-SRSComputerName,** crie um novo aplicativo HTML chamado **Set-SRSComputerName.hta** .

2.  Copie o seguinte script para o **arquivo Set-SRSComputerName.hta.** Como alternativa, você pode baixar o arquivo Set-SRSComputerName.hta [daqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).
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
3.  No console do Configuration Manager, vá para Pacotes de Gerenciamento de Aplicativos da Biblioteca de **Software** e selecione \>  \>  **Criar Pacote**.

4.  Insira as seguintes informações para criar o pacote:

    -   Nome: **SRS v2 - Set-SRSComputerName Pacote**

    -   Fabricante: **Microsoft Corporation**

    -   Versão: **1.0.0**

    -   Marque a caixa de seleção Este pacote **contém** arquivos de origem, insira o caminho para a pasta **SRS v2 - Set-SRSComputerName Pacote** e selecione **Próximo**.

5.  Selecione **Não criar um programa e** selecione **Próximo**.

6.  Revise a **página Confirmar as configurações** e selecione **Próximo**.

7.  Selecione **Fechar**.

### <a name="create-the-sysprep-package"></a>Criar o pacote Sysprep

1. Na pasta **Pacote do SRS v2 – Sysprep,** crie um novo arquivo XML chamado **Unattend.xml** .

2. Copie o seguinte texto para o arquivo **Unattend.xml** arquivo. Como alternativa, você pode baixar o arquivo Unattend.xml a [partir daqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).
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
3. No console do Configuration Manager, vá para Pacotes de Gerenciamento de Aplicativos da Biblioteca de **Software** e selecione \>  \>  **Criar Pacote**.

4. Insira as seguintes informações para criar o pacote:
   -   Nome: **SRS v2 - Pacote Sysprep**
   -   Fabricante: **Microsoft Corporation**
   -   Versão: **1.0.0**
   -   Marque a **caixa de** seleção Este pacote contém arquivos de origem, insira o caminho para a pasta Pacote **do SRS v2 – Sysprep** e selecione **Próximo**.
5. Selecione **Não criar um programa e** selecione **Próximo**.

6. Revise a **página Confirmar as configurações** e selecione **Próximo**.

7. Selecione **Fechar**.

### <a name="create-the-windows-10-enterprise-package"></a>Criar o Windows 10 Enterprise pacote

1.  Obtenha uma Windows 10 Enterprise x64 e copie o **arquivo install.wim** para a pasta **Sistemas Operacionais \\ Windows 10 Enterprise.**

2.  No console do Configuration Manager, acesse Imagens do Sistema Operacional de Sistemas Operacionais da Biblioteca de **Software** e selecione \>  \> Adicionar **Imagem do Sistema Operacional**.

3.  Especifique o caminho para **o arquivo install.wim** que você acabou de copiar e selecione **Next**.

4.  Atualize **o campo Versão** para corresponder ao número de com build da imagem Windows 10 Enterprise e selecione **Next**.

5.  Revise a **página Detalhes** e selecione **Próximo**.

6.  Selecione **Fechar**.

Para obter mais informações, consulte [Gerenciar imagens do sistema operacional com o Configuration Manager](/configmgr/osd/get-started/manage-operating-system-images).

### <a name="create-surface-pro-device-driver-packages"></a>Criar Surface Pro de driver de dispositivo

Salas do Microsoft Teams há suporte para Surface Pro e Surface Pro 4. Você precisa criar um pacote de driver para cada Surface Pro modelo que você tem em seu ambiente.

> [!IMPORTANT]
> Os drivers devem ser compatíveis com a Windows 10 Enterprise e a versão Salas do Microsoft Teams kit de implantação. Para obter mais informações, [consulte Download the latest firmware and drivers for Surface devices](/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) and Configure a [console](console.md).

1.  Baixe os drivers e firmware mais recentes.
    -   Para Surface Pro:<https://www.microsoft.com/download/details.aspx?id=55484>
    -   Para Surface Pro 4:<https://www.microsoft.com/download/details.aspx?id=49498>

2.  Extraia o driver e o firmware baixados. Abra uma janela prompt de comando e, no prompt de comando, insira um dos seguintes comandos:
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\Drivers\Surface Pro 4"`

3.  No console do Configuration Manager, vá para **Drivers** de Sistemas \> **Operacionais** da Biblioteca de Software e selecione \>  **Importar Driver**.

4.  Selecione Importar todos os drivers no seguinte caminho de rede **(UNC),** selecione a pasta de origem (por exemplo, C: \\ _Sources Drivers Surface Pro) e selecione \\ \\ **Próximo**.

5.  Na página **Especificar os detalhes dos** drivers importados, selecione todos os drivers listados e selecione Habilitar esses drivers e permitir que os computadores os **instalem.**

6.  Selecione **Categorias**, crie uma nova categoria que corresponde ao modelo Surface, selecione **OK** e selecione **Próximo**.

7.  Selecione **Novo Pacote**.

8.  Especifique o nome do pacote que corresponde ao modelo Surface Pro, insira um caminho de pasta para armazenar os arquivos do pacote de driver, selecione **OK** e selecione **Próximo**.

9.  Na página **imagens de inicialização,** certifique-se de que nenhuma imagem de inicialização está selecionada e selecione **Next**.

10. Selecione **Fechar**.

11. Vá para **Drivers de Sistemas** Operacionais da Biblioteca de Software, selecione Pasta Criar Pasta e insira um nome de pasta que corresponde ao Surface Pro modelo para o qual você acabou de importar \>  \> os drivers. **\>**

12. Mova todos os drivers importados para a pasta recém-criada para facilitar a navegação e a operação.

> [!NOTE]
> Repita as mesmas etapas para outros Surface Pro modelos que você pode ter. Para obter mais informações, consulte [Manage drivers in Configuration Manager](/configmgr/osd/get-started/manage-drivers).

### <a name="create-microsoft-teams-rooms-configuration-package"></a>Criar Salas do Microsoft Teams pacote de configuração

1.  No console do Configuration Manager, vá para Pacotes de Gerenciamento de Aplicativos da Biblioteca de **Software** e selecione \>  \>  **Criar Pacote**.

2.  Insira as seguintes informações para criar o pacote:

    -   Nome: **SRS v2 - Configurar o pacote de instalação do SRS**

    -   Fabricante: **Microsoft Corporation**

    -   Versão: **1.0.0**

    -   Marque a **caixa de** seleção Este pacote contém arquivos de origem, insira o caminho para a pasta **SRS v2 - Configure SRS Setup** e selecione **Next**.

3.  Selecione **Não criar um programa e** selecione **Próximo**.

4.  Revise a **página Confirmar as configurações** e selecione **Próximo**.

5.  Selecione **Fechar**.



## <a name="distribute-configuration-manager-packages"></a>Distribuir pacotes do Configuration Manager

Todos os pacotes devem ser distribuídos para os servidores que foram atribuídos à função de ponto de distribuição na hierarquia do Configuration Manager. Siga as instruções a seguir para iniciar a distribuição do pacote.

1.  Distribuir pacotes de software.

    1.  No console do Configuration Manager, vá para Pacotes de Gerenciamento de **Aplicativos** da Biblioteca \> **de** \> **Software.** Selecione todos os pacotes de software que você deseja distribuir e selecione **Distribuir Conteúdo**.

    2.  Revise a lista de pacotes e selecione **Next**.

    3.  Adicione todos os servidores de ponto de distribuição (ou grupos de pontos de distribuição, dependendo da hierarquia do Configuration Manager) à lista e selecione **Próximo**.

    4.  Selecione **Próximo** e, em seguida, selecione **Fechar**.

2.  Distribuir pacotes de driver.

    1.  No console do Configuration Manager, vá para Pacotes de Driver de **Sistemas** Operacionais da Biblioteca \> **de** \> Software. Selecione todos os pacotes de driver que você deseja distribuir e selecione **Distribuir Conteúdo**.

    2.  Revise a lista de pacotes e selecione **Next**.

    3.  Adicione todos os servidores de ponto de distribuição (ou grupos de pontos de distribuição, dependendo da hierarquia do Configuration Manager) à lista e selecione **Próximo**.

    4.  Selecione **Próximo** e, em seguida, selecione **Fechar**.

3.  Distribuir pacotes do sistema operacional.

    1.  No console do Configuration Manager, acesse Imagens do Sistema Operacional de **Sistemas** \> **Operacionais da** Biblioteca de \> Software. Selecione todas as imagens do sistema operacional que você deseja distribuir e selecione **Distribuir Conteúdo**.

    2.  Revise a lista de pacotes e selecione **Next**.

    3.  Adicione todos os servidores de ponto de distribuição (ou grupos de pontos de distribuição, dependendo da hierarquia do Configuration Manager) à lista e selecione **Próximo**.

    4.  Selecione **Próximo** e, em seguida, selecione **Fechar**.

> [!NOTE]
> A distribuição do pacote pode levar algum tempo, dependendo do tamanho do pacote, da hierarquia do Configuration Manager, do número de servidores de ponto de distribuição e da largura de banda disponível em sua rede.
> 
> Todos os pacotes devem ser distribuídos antes que você possa começar a implantar uma Salas do Microsoft Teams de segurança.
> 
> Você pode revisar o status da distribuição do pacote no console do Configuration Manager, indo para **Monitorar o** Status do Conteúdo de Status de \>  \> **Distribuição.**

## <a name="configuration-manager-task-sequences"></a>Sequências de tarefas do Configuration Manager

Você usa sequências de tarefas com o Configuration Manager para automatizar as etapas para implantar uma imagem do sistema operacional em um computador de destino. Para implantar uma unidade Salas do Microsoft Teams de forma automatizada, crie uma sequência de tarefas que faz referência à imagem de inicialização usada para iniciar o computador Salas do Microsoft Teams de destino, a imagem do sistema operacional Windows 10 Enterprise que você deseja instalar e qualquer outro conteúdo adicional, como outros aplicativos ou atualizações de software.

### <a name="import-the-sample-task-sequence"></a>Importar a sequência de tarefas de exemplo

Você pode baixar e importar facilmente uma sequência de tarefas de exemplo e personalizá-la para atender às suas necessidades.

1.  [**Baixe**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) a sequência de tarefas de exemplo e copie o arquivo zip baixado para um local compartilhado.
2.  No console do Configuration Manager, vá para **Sequências** de Tarefas de Sistemas Operacionais da Biblioteca de Software e selecione \>  \> Importar Sequência **de Tarefas.**

3.  Selecione **Procurar**, vá para o local da pasta compartilhada que você usou na etapa 1, selecione o arquivo Salas do Microsoft Teams **Deployment (EN-US).zip** e selecione **Próximo**.

4.  De **definir Ação** para Criar **Novo** e, em seguida, selecione **Próximo**.

5.  Confirme as configurações e selecione **Next**.

6.  Selecione **Fechar**.

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a>Valide se os pacotes de referência estão vinculados corretamente a cada etapa de sequência de tarefas.

1. Selecione a sequência de tarefas importada e selecione **Editar**.

    O Editor de Sequência de Tarefas abre e exibe cada etapa sequencial que você precisa para implantar e configurar uma Salas do Microsoft Teams unidade.

2. Ande por cada etapa e conclua as atualizações recomendadas:

   1. **Reiniciar no Windows PE**: esta etapa é reiniciada e inicializa o computador Windows PXE. Nenhuma alteração é necessária para esta etapa.

   2. **Disco de Partição 0 – UEFI**: Esta etapa apaga a configuração do disco e cria partições com base nas configurações configuradas. Recomendamos que você não faça alterações nesta etapa.

   3. **Definir Nome do Computador SRS**: Esta etapa inclui um aplicativo HTML para fornecer uma interface do usuário para definir um nome de computador para a unidade Salas do Microsoft Teams durante a implantação.
      -  Esta é uma etapa opcional, mas só poderá ser desabilitada se você quiser gerenciar a nomeação do computador por meio de um processo alternativo.
      -  Verifique se o **pacote SRS v2 - Set-SRSComputerName** está selecionado. Se não estiver, navegue até o pacote e selecione-o.

   4. **Aplicar Sistema Operacional**: esta etapa especifica a imagem do sistema operacional a ser implantada e o arquivo de resposta Sysprep sem supervisão a ser usado.
      -  Verifique se o arquivo de Windows 10 Enterprise de imagem do sistema operacional está selecionado.
      -  Verifique se Usar um arquivo de resposta autônoma ou **Sysprep** para uma instalação personalizada está habilitado e o **Pacote SRS v2 - Sysprep** está selecionado. Verifique também se **o Nome do** Arquivo está definido como **unattend.xml**.

   5. **Aplicar Windows Configurações**: Esta etapa coleta informações sobre a instalação Windows local.
      -  Forneça informações de licenciamento e registro, incluindo a chave do produto, a senha da conta do administrador local e o fuso horário (dependendo das suas necessidades).

   6. **Aplicar rede Configurações**: Esta etapa permite especificar um grupo de trabalho ou nome de domínio do Active Directory e uma unidade organizacional.
      > [!NOTE]
      > Consulte Skype considerações de junção de domínio do Sistema de Sala para ações [recomendadas](domain-joining-considerations.md) que você precisa tomar na implantação de unidades Salas do Microsoft Teams como membros de um domínio do Diretório actve.
   7. **Aplicar drivers:** Esta etapa e suas sub-etapas são usadas para implantar drivers de dispositivo e firmware aplicáveis com base no Surface Pro modelo que você tem. Atualize cada etapa para especificar o pacote de driver relevante associado a essa implantação.
      -   Cada pacote de driver é configurado para aproveitar Windows de Instrumentação de Gerenciamento (WMI) para implantar drivers e firmware relevantes com base na Surface Pro e modelo.
      -   É altamente recomendável que você não altere a configuração desses drivers, caso contrário, a implantação pode falhar.

   8. **Configurar o Windows e o Configuration Manager:** esta etapa implanta e configura o cliente do Configuration Manager. Atualize esta etapa para especificar o Pacote de Cliente do Configuration Manager integrado.

   9. **Instalar Certificado Raiz**: esta etapa distribui o certificado raiz para dispositivos não ingressados no domínio e, portanto, é opcional e desabilitado por padrão.
      -   Habilita esta etapa se precisar implantar um certificado raiz nas unidades Salas do Microsoft Teams.
      -   Se você precisar executar essa etapa, verifique se o **SRS v2 – Pacote** de Certificado Raiz e Desabilitar o redirecionamento do sistema de arquivos de **64 bits** está selecionado.

   10. **Instalar e configurar o Agente** de Monitoramento: esta etapa instala a versão de 64 bits do agente monitor Microsoft Azure e configura o agente para se conectar ao seu espaço de trabalho do Log Analytics.
       -   Esta etapa é desabilitada por padrão. Habilita esta etapa somente se você for usar o Agente de Monitoramento para monitorar a saúde de suas Salas do Microsoft Teams unidades.
       -   Edite esta etapa e atualize os parâmetros de linha de comando para especificar a **ID** do Espaço de Trabalho e **a Chave do Espaço de Trabalho.**
       -   Consulte [Configure test devices for Azure Monitoring](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) para obter mais informações sobre como obter a ID do Espaço de Trabalho do Pacote de Gerenciamento de Operações e a chave primária.
       -   Verifique se o **srs v2 – Microsoft Monitoring Agent pacote** e desabilitar o redirecionamento do sistema de arquivos de **64** bits estão selecionados.
       -   Para obter mais informações sobre o monitoramento da saúde da implantação do Salas do Microsoft Teams, consulte [Plan Salas do Microsoft Teams management with Azure Monitor](azure-monitor-plan.md), Deploy Salas do Microsoft Teams management with [Azure Monitor](azure-monitor-deploy.md) and Manage Salas do Microsoft Teams devices with [Azure Monitor](azure-monitor-manage.md).

   11. **Copiar arquivos de configuração do SRS v2**: Esta etapa copia os arquivos de configuração e configuração necessários do kit de implantação Salas do Microsoft Teams para o disco rígido local. Nenhuma personalização é necessária para esta etapa.
       -   Verifique se o **SRS v2 – Pacote de Aplicativos SRS** e Desabilitar o redirecionamento do sistema de arquivos de **64 bits** estão selecionados.

   12. **Install-SRSv2-OS-Updates**: Esta etapa implanta todas as atualizações obrigatórias do sistema operacional necessárias com Salas do Microsoft Teams implantação. Siga este procedimento:
       -   Verifique [Configurar um console Salas do Microsoft Teams](console.md) para ver quais atualizações são necessárias.
       -   Verifique se o pacote de atualizações do SISTEMA OPERACIONAL do **SRS v2** inclui todas as atualizações necessárias.
       -   Verifique se o Pacote de Atualizações do SISTEMA OPERACIONAL do **SRS v2** está selecionado.
       -   Verifique se a política de execução do PowerShell está definida como **Bypass**.

   13. **Reiniciar Computador**: esta etapa reinicia o computador depois que as atualizações obrigatórias do sistema operacional são instaladas. Nenhuma personalização é necessária para esta etapa.

   14. **Configurar Windows componentes**: esta etapa configura os recursos de Windows necessários. Nenhuma personalização é necessária para esta etapa.

   15. **Reiniciar Computador**: esta etapa reinicia o computador depois que os recursos Windows são configurados. Nenhuma personalização é necessária para esta etapa.

   16. **Adicionar Usuário Skype Local:** esta etapa cria a conta local Skype usada para entrar automaticamente no Windows e iniciar o aplicativo Salas do Microsoft Teams local. Esta etapa não tem nenhum pacote de software associado a ele e nenhuma personalização é necessária para ele.

   17. **Configurar e configurar o aplicativo SRS**: esta etapa configura a instalação do aplicativo Salas do Microsoft Teams para a próxima inicialização do sistema operacional.
       -   Verifique se o **SRS v2 – Configurar o** Pacote de Instalação do SRS e Desabilitar o redirecionamento do sistema de arquivos de **64** bits está selecionado.

> [!IMPORTANT]
> É muito importante que as etapas da sequência de tarefas devem estar na ordem fornecida. Modificar a ordem das etapas ou configurar etapas adicionais pode quebrar a implantação.
>
> **Configurar e configurar a etapa** do aplicativo SRS deve ser a última etapa da sequência de tarefas, caso contrário, a implantação poderá falhar.

### <a name="create-deployment-for-the-task-sequence"></a>Criar implantação para a sequência de tarefas

1. Selecione a sequência de tarefas e selecione **Implantar**.

2. Selecione **Procurar** para selecionar o conjunto de destinos para implantação.

3. Selecione **Todos os Computadores Desconhecidos** e selecione **OK**.

4. Selecione **Próximo**.

5. Selecione **Disponível** na **listada** Finalidade.

6. Selecione **Somente Mídia e PXE** na lista **Disponibilizar** para a lista a seguir e selecione **Next**.
   > [!WARNING]
   > É muito importante que **Purpose** seja definido como **Disponível**. Certifique-se de **que a Finalidade** NÃO **está** definida **como Obrigatório**. Além disso, certifique-se de selecionar **Somente Mídia e PXE** no **make available to the following**.
   >
   > Definir esses valores para outra coisa pode fazer com que todos os computadores recebam a imagem Salas do Microsoft Teams de implantação quando inicializadas.
7. Não especifique nenhum cronograma e selecione **Next**.

8. Não altere nada na seção Experiência do **Usuário** e selecione **Next**.

9. Não altere nada na seção **Alertas** e selecione **Next**.

10. Não altere nada na seção **Pontos de Distribuição** e selecione **Next**.

11. Confirme as configurações e selecione **Next**.

12. Selecione **Fechar**.

**Validar e solucionar problemas da solução**

Depois de concluir as Microsoft Endpoint Configuration Manager de tarefas, você precisará executar uma execução de teste para validar se a sequência de tarefas pode implantar e configurar Salas do Microsoft Teams unidades.

1.  Conexão o dispositivo de teste para a rede com fio usando um dos adaptadores Ethernet com suporte ou usando o encaixe Surface. Se a funcionalidade de inicialização PXE não tiver sido configurada para seu [](/configmgr/osd/deploy-use/create-bootable-media) ambiente, você poderá usar a imagem de inicialização na unidade flash USB que você criou anteriormente para inicializar a partir de USB e se conectar ao Configuration Manager.

2.  Acesse o firmware e inicie a inicialização PXE:

    1.  Verifique se o dispositivo Surface está desligado.

    2.  Pressione e segure o **botão Volume Up.**

    3.  Pressione e solte o **botão Ligar.**

    4.  Depois que o dispositivo começar a ser inicializado, solte o **botão Volume Up.**

    5.  Selecione **Configuração de inicialização**.

    6.  Siga um destes procedimentos:

        -   Selecione **inicialização PXE** e arraste-a para a parte superior da lista. Como alternativa, você pode passar o dedo para a esquerda no adaptador de rede para inicializar o dispositivo imediatamente. Isso não afetará a ordem de inicialização.
        -   Selecione a unidade flash USB que contém a mídia de inicialização.

3.  Selecione **Sair** e, em seguida, selecione **Reiniciar Agora**.

4.  Quando solicitado, selecione **Enter for** network boot service.

5.  Windows O PE será carregado na memória e o Assistente de Sequência de Tarefas será a iniciar. Selecione **Próximo** para continuar.

6.  Selecione a sequência de tarefas que você importou anteriormente e selecione **Next**.

7.  Depois que a configuração do disco for aplicada, você será solicitado a especificar um nome de computador para o dispositivo. A interface do usuário exibirá um nome de computador recomendado com base no número de série do Surface Pro dispositivo. Você pode aceitar o nome proposto ou especificar um novo. Siga as instruções na tela de atribuição do nome do computador. Quando você seleciona **Aceitar**, a implantação começa.

8.  O restante do processo de implantação é automático e não solicita mais entrada do usuário.

9.  Depois que a sequência de tarefas de implantação terminar de configurar o dispositivo, você verá a tela de configuração a seguir que solicita que você configure as configurações Salas do Microsoft Teams aplicativo.

    ![Tela de instalação inicial para Salas do Microsoft Teams aplicativo.](../media/room-systems-scale-image2.png)

10.  Conecte o Surface Pro no console Salas do Microsoft Teams e configure as configurações do aplicativo.

11.  Valide se os recursos listados [Salas do Microsoft Teams ajuda estão](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) funcionando no dispositivo implantado.


Para solucionar problemas de uma instalação com falha, verifique o **arquivo SMSTS.log,** que registra todas as etapas executadas em uma sequência de tarefas do Configuration Manager.

O arquivo SMSTS.log é armazenado em um de vários caminhos, dependendo do estágio do processo de com build. Verifique a tabela a seguir para identificar o caminho para o arquivo SMSTS.log.


| **Fase de implantação**                                                            | **Caminho de log de sequência de tarefas**                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| WinPE, antes do formato HDD                                                        | X: \\ Windows \\ \\ smstslog \\ temp smsts.log             |
| WinPE, após o formato HDD                                                         | C: \\ _SMSTaskSequence \\ Logs \\ Smstslog \\ smsts.log    |
| Sistema operacional implantado, antes da instalação do agente do Configuration Manager | c: \\ _SMSTaskSequence \\ Logs \\ Smstslog \\ smsts.log    |
| Sistema operacional e o agente do Configuration Manager implantado                   | %windir% \\ System32 \\ ccm \\ logs \\ Smstslog \\ smsts.log |
| Execução da sequência de tarefas concluída                                                | %windir% \\ System32 \\ ccm \\ logs \\ smsts.log           |

> [!TIP]
> Você pode selecionar **F8** a qualquer momento durante a sequência de tarefas para abrir um console de comando e obter acesso ao arquivo SMSTS.log.

Para solucionar problemas de inicialização PXE, verifique os dois arquivos de log no servidor do Configuration Manager que são específicos das ações PXE:

-   **Pxecontrol.log**, localizado no diretório de logs de instalação do Configuration Manager

-   **Smspxe.log**, localizado no diretório de logs do Ponto de Gerenciamento do Configuration Manager (MP)

Para ver uma lista completa dos arquivos de log que você pode usar para solucionar problemas adicionais da instalação do Configuration Manager, consulte a referência de arquivo Microsoft Endpoint Configuration Manager [Log.](/configmgr/core/plan-design/hierarchy/log-files)
