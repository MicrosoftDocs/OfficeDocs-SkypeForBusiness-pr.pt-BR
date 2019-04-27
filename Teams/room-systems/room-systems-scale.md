---
title: Implantar o Microsoft equipes salas usando o System Center Configuration Manager
author: jambirk
ms.author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection: M365-voice
description: Leia este tópico para saber mais sobre como implantar o Microsoft equipes salas em implantações de grande escala.
ms.openlocfilehash: f8770a98cb08e33676f7079aa1a60743ea68b1dd
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362607"
---
# <a name="deploy-microsoft-teams-rooms-by-using-system-center-configuration-manager"></a>Implantar o Microsoft equipes salas usando o System Center Configuration Manager

Este artigo fornece todas as informações necessárias para criar as implantações de salas de equipes da Microsoft usando o System Center Configuration Manager.

Com os métodos de fácil utilização fornecidos pelo System Center Configuration Manager, você pode implantar o sistema operacional e outros aplicativos em vários dispositivos de destino.

Usar a abordagem ilustrada abaixo para orientá-lo a configuração do Configuration Manager e personalize os pacotes de amostra e os scripts fornecidos no decorrer deste guia, conforme necessário para sua organização.

![Processo de implantação de salas de equipes da Microsoft usando o Configuration Manager](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> Essa solução foi testada apenas com implantações baseadas em Surface Pro. Siga as diretrizes do fabricante para configurações que não são baseadas em Surface Pro.

## <a name="validate-prerequisites"></a>Valide os pré-requisitos

Para implantar o Microsoft equipes salas com o Configuration Manager, certifique-se de que você atende os seguintes pré-requisitos e requisitos.

### <a name="system-center-configuration-manager-requirements"></a>Requisitos do System Center Configuration Manager

-   Versão do System Center Configuration Manager deve ser de pelo menos 1706 ou acima. É recomendável usar 1710 ou posterior. Confira o [suporte para o Windows 10 no System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) para saber mais sobre as versões do Windows 10 Configuration Manager oferece suporte.

-   Uma versão compatível do Windows Assessment e Kit de implantação (ADK) para Windows 10 deve ser instalada. Consulte as versões do [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) que você pode usar com diferentes versões do Configuration Manager e certifique-se de que sua implantação incluir a versão correta.

-   Os servidores de sistema do site devem ser atribuídos a função de ponto de distribuição e as imagens de inicialização devem ser habilitadas para [preboot suporte do ambiente (PXE) de execução](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) habilitar implantações iniciadas de rede. Se o suporte a PXE não estiver habilitado, você pode usar a [mídia inicializável](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) para suas implantações.

-   Uma conta de acesso de rede deve ser configurada para oferecer suporte a novos cenários de implantação de computador (bare metal). Para saber mais sobre a configuração de uma conta de acesso de rede, consulte [Gerenciar contas para acessar o conteúdo no System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).

-   Recomendamos que você habilite o [suporte ao multicast](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), se você provavelmente precisará implantar a mesma imagem de salas de equipes da Microsoft em várias unidades ao mesmo tempo.

### <a name="networking-requirements"></a>Requisitos de rede

-   Sua rede deve ter um servidor Dynamic Host Configuration Protocol (DHCP), configurado para distribuição automática de endereço IP para as sub-redes onde unidades de salas de equipes da Microsoft serão implantadas.

    > [!NOTE]
    > Duração de concessão DHCP deve ser definida como um valor maior que a duração de implantação de imagem. Caso contrário, a implantação pode falhar.

-   Sua rede, incluindo comutadores e LANs virtuais (VLANs), deve ser configurado para oferecer suporte a PXE. Consulte seu fornecedor de rede para obter mais informações sobre a configuração IP Helper e PXE. Como alternativa, você pode usar [mídia inicializável](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) para suas implantações, se o suporte PXE não está habilitado.

    > [!NOTE]
    > Para Surface Pro dispositivos, inicialização a partir da rede (inicialização PXE) só são suportados quando você usa um adaptador de Ethernet ou estação de encaixe da Microsoft. Adaptadores de Ethernet de terceiros não oferecem suporte a inicialização PXE com Surface Pro. Para obter mais informações, consulte [implantação de superfície e adaptadores Ethernet](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) .

## <a name="configure-system-center-configuration-manager-for-operating-system-deployment"></a>Configurar o System Center Configuration Manager para implantação do sistema operacional

Este artigo pressupõe que você já possui uma implantação do System Center Configuration Manager íntegro e não detalhes de todas as etapas necessárias para implantar e configurar o Gerenciador de configuração do zero. A [documentação e as diretrizes de configuração](https://docs.microsoft.com/sccm/) no System Center Configuration Manager é um ótimo recurso; Recomendamos que você comece com esses recursos, se você ainda não tenha implantado o Configuration Manager.

Use as instruções a seguir para verificar se os recursos de implantação (OSD) do sistema operacional estão configurados corretamente.

### <a name="validate-and-upgrade-configuration-manager"></a>Validar e atualizar o Configuration Manager

1.  No console do Configuration Manager, vá para **Administração** \> **atualizações e manutenção**.

2.  Verifique a compilação instalada e atualizações aplicáveis que ainda não tenham sido instaladas.

3.  Revise o [suporte para Windows 10 no System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); Se você precisar atualizar a implantação, selecione a atualização que você deseja instalar e, em seguida, selecione **Baixar**.

4.  Quando o download for concluído, selecione a atualização e, em seguida, selecione **Instalar o pacote de atualização**.

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a>Configurar os pontos de distribuição para oferecer suporte a PXE e multicast

1.  No console do Configuration Manager, vá para **Administração** \> **Pontos de distribuição**.

2.  Selecione o servidor de ponto de distribuição que atender a implantação de salas de equipes da Microsoft e selecione **Propriedades**.

3.  Selecione a guia **PXE** e certifique-se de que as configurações a seguir estão habilitadas:
    -   Habilitar o suporte a PXE para clientes
    -   Permitir que esse ponto de distribuição responder às solicitações de entrada PXE
    -   Habilitar o suporte de computador desconhecido

4.  *Opcional:* Para habilitar o suporte ao multicast, selecione a guia **Multicast** e certifique-se de que as configurações a seguir estão habilitadas:
    -   Habilitar multicast simultaneamente enviar dados para vários clientes
    -   Configurar o intervalo de portas UDP conforme recomendação da sua equipe de rede

### <a name="configure-the-network-access-account"></a>Configurar a conta de acesso de rede

1.  No console do Configuration Manager, vá para **Administração** \> **Configuração de Site** \> **Sites**e selecione o site.

2.  No grupo **configurações** , selecione **Configurar componentes de Site** \> **A distribuição de Software**.

3.  Selecione a guia de **Conta de acesso de rede** Set up uma ou mais contas e selecione **Okey**.

> [!NOTE]
> As contas não precisam quaisquer direitos especiais, exceto para o **acesso a este computador a partir da rede** diretamente no servidor de ponto de distribuição. Uma conta de usuário de domínio genérico será apropriada. Para obter mais informações, consulte [Gerenciar contas para acessar o conteúdo no System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).

### <a name="configure-a-boot-image"></a>Configurar uma imagem de inicialização

1.  No console do Configuration Manager, vá para **A biblioteca de Software** \> **sistema operacional** \> **Imagens de inicialização**.

2.  Selecione a **imagem de inicialização (x64)** e selecione **Propriedades**.

3.  Selecione a guia **Fonte de dados** e habilite **implantar essa imagem de inicialização do ponto de distribuição habilitado para PXE**.

4.  Selecione a guia **Componentes opcionais** para instalar os componentes necessários:

    1.  Selecione o ícone de estrela e procurar **HTML (HTA WinPE)**

    2.  Selecione **Okey** para adicionar suporte a aplicativos em HTML para a imagem de inicialização.

5.  *Opcional:* Para personalizar a experiência de implantação, selecione a guia de **personalização** .
    -   Habilite o **comando suporte (somente para teste)** se você deseja que tenham acesso a um prompt de comando durante a implantação. Quando esta opção estiver ativada, você pode iniciar um prompt de comando, selecionando **F8** a qualquer momento durante a implantação.
    -   Você também pode especificar uma imagem de plano de fundo personalizado a ser exibida durante a implantação. Para definir uma imagem, habilitar **especificar o arquivo de imagem de plano de fundo personalizado (caminho UNC** e selecione seu plano de fundo.

6.  Quando solicitado, selecione **Sim** e distribuir a imagem de inicialização atualizada para seus pontos de distribuição.

Para obter mais informações, consulte [imagens de inicialização de gerenciar com o System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).

> [!NOTE]
> Você pode criar uma mídia USB inicializável para lançar implantações de baseadas em sequência de tarefa Configuration Manager para ambientes que não oferece suporte a PXE. A mídia inicializável contém apenas a imagem de inicialização, comandos prestart opcionais e seus arquivos necessários e binários do Configuration Manager para oferecer suporte à inicialização no Windows PE e conectando-se ao Gerenciador de configuração para o restante do processo de implantação. Para obter mais informações, consulte [como criar uma mídia inicializável](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).

## <a name="create-configuration-manager-packages"></a>Crie pacotes do Configuration Manager

Gerenciador de configuração requer um número de pacotes para implantar e configurar as unidades de salas de equipes da Microsoft.

Você precisa criar e configurar os pacotes a seguir e, em seguida, distribuí-las para os sistemas de site do Configuration Manager que tiverem sido atribuídos a função de servidor do ponto de distribuição.

| **Nome do pacote**                     | **Tipo**               | **Descrição**                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| SRS v2 - SRS pacote de aplicativos     | Pacote de software       | Pacote para o kit de implantação de salas de equipes da Microsoft                                      |
| SRS v2 - pacote Sysprep             | Pacote de software       | Pacote para o Unattended.xml personalizado configurar unidades de salas de equipes da Microsoft            |
| SRS v2 - Set-SRSComputerName pacote | Pacote de software       | Pacote para o aplicativo HTML (HTA) atribuir um nome de computador durante a implantação    |
| SRS v2 - configurar a instalação do SRS         | Pacote de software       | Pacote para configurar a implantação do aplicativo Microsoft equipes salas                          |
| SRS v2 - pacote de atualizações de sistema operacional          | Pacote de software       | Pacote para implantar as atualizações obrigatórias do sistema operacional                                      |
| SRS v2 - pacote do certificado raiz    | Pacote de software       | Opcional - pacote para implantar o certificado raiz (não é necessário para unidades de domínio)  |
| SRS v2 - Microsoft pacote do agente de monitoramento | Pacote de software       | Opcional - pacote para implantar e configurar o agente do pacote de gerenciamento de operações do Microsoft|
| SRS v2 - pacote de plano de fundo do WinPE    | Pacote de software       | Pacote para a imagem de plano de fundo personalizado a ser usada com imagens de inicialização                           |
| Windows 10 Enterprise                | Imagem do sistema operacional | Pacote para o arquivo de instalação do sistema operacional (WIM)                          |
| Surface Pro                          | Pacote de driver         | Pacote para drivers de dispositivo e firmware Microsoft Surface Pro                     |
| Surface Pro 4                        | Pacote de driver         | Pacote para drivers de dispositivo e firmware para 4 do Microsoft Surface Pro                   |

Para obter mais informações, consulte [pacotes e programas no System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).

### <a name="create-folders-for-the-package-source-files"></a>Criar arquivos de origem de pastas para o pacote

Gerenciador de configuração requer os arquivos de origem de pacote para ser organizados em uma estrutura de pasta específica, eles são criados pela primeira vez e quando os campos são atualizados.

Crie a seguinte estrutura de pasta no site de administração central do System Center Configuration Manager ou sites primário ou em um compartilhamento de servidor que você está usando para arquivos de origem do pacote de host:

-   SRS v2 - Microsoft pacote do agente de monitoramento
-   SRS v2 - pacote de atualizações de sistema operacional
-   SRS v2 - pacote do certificado raiz
-   SRS v2 - Set-SRSComputerName pacote
-   SRS v2 - SRS pacote de aplicativos
-   SRS v2 - configurar a instalação do SRS
-   SRS v2 - pacote Sysprep
-   Drivers
    -   Surface Pro
    -   Surface Pro 4
-   Sistemas operacionais
    -   Windows 10 Enterprise

> [!TIP]
> Você também pode [Baixar](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) e usar o arquivo zip que inclui a estrutura de pasta para os pacotes e os scripts que você precisará usar o modelo de sequência de tarefa, que você precisa importar.

### <a name="create-the-monitoring-agent-package"></a>Criar o pacote do agente de monitoramento

1. Baixe o agente de monitoramento da <https://go.microsoft.com/fwlink/?LinkId=828603>.

2. Extraia o pacote para a pasta **SRS v2 - Microsoft Monitoring Agent Package** abrindo uma janela de Prompt de comando e inserindo **/c de MMASetup-AMD64.exe:** no prompt de comando.

3. No console do Configuration Manager, vá para **A biblioteca de Software** \> **Gerenciamento de aplicativos** \> **pacotes**e, em seguida, selecione **Criar pacote**.

4. Insira as informações a seguir para criar o pacote:

   - Nome<strong>: SRS v2 - Microsoft Monitoring Agent pacote</strong>

   - Fabricante<strong>: Microsoft Corporation</strong>

   - Versão<strong>: 8.1.11081.0</strong> (Insira a versão do arquivo de instalação baixado)

   - Marque a caixa de seleção **Este pacote contém arquivos de origem** , insira o caminho da pasta **SRS v2 - pacote de agente de monitoramento Microsoft** e selecione **Avançar**.

5. Selecione **não criar um programa**e selecione **Avançar**.

6. Revise a página **Confirme as configurações** e selecione **Avançar**.

7. Selecione **Fechar**.

### <a name="create-the-operating-system-updates-package"></a>Crie o pacote de atualizações do sistema operacional

1. Na pasta **SRS v2 - pacote de atualizações do sistema operacional** , crie um novo script do PowerShell chamado **Install-SRSv2 SO Updates.ps1**.

2. Copie o script abaixo para o script **Install-SRSv2 SO Updates.ps1** . Como alternativa, você pode baixar o script Install-SRSv2 SO Updates.ps1 [aqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).
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
3. Baixe os pacotes do Windows Update obrigatórios para a mesma pasta.
   > [!NOTE]
   > No momento em que este artigo foi publicado, [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) era necessária. Verifique se [Configure um console de salas de equipes da Microsoft](console.md), para ver se quaisquer outras atualizações são necessárias.

4. No console do Configuration Manager, vá para **A biblioteca de Software** \> **Gerenciamento de aplicativos** \> **pacotes**e, em seguida, selecione **Criar pacote**.

5. Insira as informações a seguir para criar o pacote:
   -   Nome: **SRS v2 – SO atualiza o pacote**
   -   Fabricante: **Microsoft Corporation**
   -   Versão: **1.0.0**
   -   Marque a caixa de seleção **Este pacote contém arquivos de origem** , insira o caminho da pasta **SRS v2 - pacote de atualizações do sistema operacional** e selecione **Avançar**.

6. Selecione **não criar um programa**e selecione **Avançar**.

7. Revise a página **Confirme as configurações** e selecione **Avançar**.

8. Selecione **Fechar**.

### <a name="create-the-root-certificate-package-optional"></a>Criar o pacote do certificado raiz (opcional)

Você criar este pacote para distribuir o certificado raiz para dispositivos que não estar associado a um domínio do Active Directory. Crie este pacote somente se as seguintes condições se aplicam:
-   Sua implantação incluir local Lync ou Skype para Business Server.
-   Unidades de salas de equipes da Microsoft são configuradas para trabalhar em um grupo de trabalho em vez de um membro do domínio.

1.  Copie o certificado raiz para a pasta **SRS v2 – pacote do certificado raiz** .

2.  No console do Configuration Manager, vá para **A biblioteca de Software** \> **Gerenciamento de aplicativos** \> **pacotes**e, em seguida, selecione **Criar pacote**.

3.  Insira as informações a seguir para criar o pacote:
    -   Nome: **SRS v2 – pacote do certificado raiz**
    -   Fabricante: *nome da sua organização*
    -   Versão: **1.0.0**
    -   Marque a caixa de seleção **Este pacote contém arquivos de origem** , insira o caminho da pasta **SRS v2 – pacote do certificado raiz** e selecione **Avançar**.

4.  Selecione **não criar um programa**e selecione **Avançar**.

5.  Revise a página **Confirme as configurações** e selecione **Avançar**.

6.  Selecione **Fechar**.

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a>Criar um pacote do kit de implantação do Microsoft equipes salas

1.  Baixe a versão mais recente do **kit de implantação do Microsoft equipes salas** de <https://go.microsoft.com/fwlink/?linkid=851168>e instalá-lo a uma estação de trabalho.

2.  Copiar o conteúdo de **c:\\arquivos de programa (x86)\\Kit de implantação do sistema do Skype sala** para a pasta **SRS v2 - SRS pacote de aplicativos** .

3.  No console do Configuration Manager, vá para **A biblioteca de Software** \> **Gerenciamento de aplicativos** \> **pacotes**e, em seguida, selecione **Criar pacote**.

4.  Insira as informações a seguir para criar o pacote:
    -   Nome: **SRS v2 – SRS pacote de aplicativos**
    -   Fabricante: **Microsoft Corporation**
    -   Versão: **3.1.104.0** (Insira a versão do arquivo de instalação baixado)
    -   Marque a caixa de seleção **Este pacote contém arquivos de origem** , insira o caminho da pasta **SRS v2 – SRS pacote de aplicativos** e selecione **Avançar**.
5.  Selecione **não criar um programa**e selecione **Avançar**.

6.  Revise a página **Confirme as configurações** e selecione **Avançar**.

7.  Selecione **Fechar**.

### <a name="create-the-computer-name-assignment-package"></a>Crie o pacote de atribuição de nome de computador

1.  Na pasta **SRS v2 - Set-SRSComputerName pacote** , crie um novo aplicativo de HTML chamado **Set-SRSComputerName.hta** .

2.  Copie o script a seguir para o arquivo de **Set-SRSComputerName.hta** . Como alternativa, você pode baixar o arquivo Set-SRSComputerName.hta [aqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).
    ```
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
3.  No console do Configuration Manager, vá para **A biblioteca de Software** \> **Gerenciamento de aplicativos** \> **pacotes**e, em seguida, selecione **Criar pacote**.

4.  Insira as informações a seguir para criar o pacote:

    -   Nome: **SRS v2 - Set-SRSComputerName pacote**

    -   Fabricante: **Microsoft Corporation**

    -   Versão: **1.0.0**

    -   Marque a caixa de seleção **Este pacote contém arquivos de origem** , insira o caminho da pasta **SRS v2 - Set-SRSComputerName pacote** e selecione **Avançar**.

5.  Selecione **não criar um programa**e selecione **Avançar**.

6.  Revise a página **Confirme as configurações** e selecione **Avançar**.

7.  Selecione **Fechar**.

### <a name="create-the-sysprep-package"></a>Crie o pacote de Sysprep

1. Na pasta **SRS v2 – pacote Sysprep** , crie um novo arquivo XML denominado **Unattend. XML** .

2. Copie o seguinte texto para o arquivo de **Unattend. XML** . Como alternativa, você pode baixar o arquivo Unattend [aqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).
   ```
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
3. No console do Configuration Manager, vá para **A biblioteca de Software** \> **Gerenciamento de aplicativos** \> **pacotes**e, em seguida, selecione **Criar pacote**.

4. Insira as informações a seguir para criar o pacote:
   -   Nome: **SRS v2 - pacote Sysprep**
   -   Fabricante: **Microsoft Corporation**
   -   Versão: **1.0.0**
   -   Marque a caixa de seleção **Este pacote contém arquivos de origem** , insira o caminho da pasta **SRS v2 – pacote Sysprep** e selecione **Avançar**.
5. Selecione **não criar um programa**e selecione **Avançar**.

6. Revise a página **Confirme as configurações** e selecione **Avançar**.

7. Selecione **Fechar**.

### <a name="create-the-windows-10-enterprise-package"></a>Criar um pacote do Windows 10 Enterprise

1.  Obtenha uma mídia Windows 10 Enterprise x64 e copie o arquivo **WIM** para a **sistemas operacionais\\Windows 10 Enterprise** pasta.

2.  No console do Configuration Manager, vá para **A biblioteca de Software** \> **sistemas operacionais** \> **Imagens de sistema operacional**e selecione **Adicionar a imagem do sistema operacional**.

3.  Especifique o caminho para o arquivo **WIM** que você acabou de copiar e selecione **Avançar**.

4.  Atualize o campo de **versão** para coincidir com o número de compilação da imagem do Windows 10 Enterprise e selecione **Avançar**.

5.  Revise a página de **detalhes** e selecione **Avançar**.

6.  Selecione **Fechar**.

Para obter mais informações, consulte [Gerenciar imagens do sistema operacional com o System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).

### <a name="create-surface-pro-device-driver-packages"></a>Crie pacotes de driver de dispositivo Surface Pro

Salas de equipes da Microsoft é suportada para Surface Pro e 4 do Surface Pro. Você precisará criar um pacote de driver para cada modelo Surface Pro, que você tem em seu ambiente.

> [!IMPORTANT]
> Os drivers devem ser compatíveis com a compilação do Windows 10 Enterprise e a versão do kit de implantação Microsoft equipes salas. Para obter mais informações, consulte [Baixe o firmware mais recente e a drivers para dispositivos de superfície](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) e [Configure um console](console.md).

1.  Baixe os drivers e o firmware mais recente.
    -   Para Surface Pro:<https://www.microsoft.com/download/details.aspx?id=55484>
    -   Para Surface Pro 4:<https://www.microsoft.com/download/details.aspx?id=49498>

2.  Extraia o driver baixado e firmware. Abra uma janela de Prompt de comando e no prompt de comando, insira um dos seguintes comandos:
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  No console do Configuration Manager, vá para **A biblioteca de Software** \> **sistemas operacionais** \> **Drivers**e, em seguida, selecione **O Driver de importação**.

4.  Selecione **importar todos os drivers no seguinte caminho de rede (UNC)**, selecione a pasta de origem (por exemplo, c\\_Sources\\Drivers\\Surface Pro) e selecione **Avançar**.

5.  Na página **especificar os detalhes para os drivers importados** , selecione todos os drivers listados e selecione **Habilitar esses drivers e permitir que os computadores instalá-los**.

6.  Selecione **categorias**, criar uma nova categoria que coincide com o modelo de superfície, selecione **Okey**e selecione **Avançar**.

7.  Selecione o **novo pacote**.

8.  Especifique o nome do pacote que coincide com o modelo Surface Pro, insira um caminho de pasta para armazenar os arquivos do pacote de driver em, selecione **Okey**e selecione **Avançar**.

9.  Na página de **imagens de inicialização** , certifique-se de que nenhum imagens de inicialização são selecionadas e selecione **Avançar**.

10. Selecione **Fechar**.

11. Vá para a **Biblioteca de Software** \> **sistemas operacionais** \> **Drivers**, selecione **pasta \> criar pasta**e insira um nome de pasta que coincide com o modelo Surface Pro que você acabou de importar os drivers para.

12. Mova todos os drivers importados para a pasta recém-criada para fácil navegação e a operação.

> [!NOTE]
> Repita as mesmas etapas para outros modelos Surface Pro, que talvez seja necessário. Para obter mais informações, consulte [Gerenciar drivers no System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).

### <a name="create-microsoft-teams-rooms-configuration-package"></a>Criar um pacote de configuração de salas de equipes da Microsoft

1.  No console do Configuration Manager, vá para **A biblioteca de Software** \> **Gerenciamento de aplicativos** \> **pacotes**e, em seguida, selecione **Criar pacote**.

2.  Insira as informações a seguir para criar o pacote:

    -   Nome: **SRS v2 - configurar o pacote de instalação do SRS**

    -   Fabricante: **Microsoft Corporation**

    -   Versão: **1.0.0**

    -   Marque a caixa de seleção **Este pacote contém arquivos de origem** , insira o caminho da pasta **SRS v2 - configurar SRS instalação** e selecione **Avançar**.

3.  Selecione **não criar um programa**e selecione **Avançar**.

4.  Revise a página **Confirme as configurações** e selecione **Avançar**.

5.  Selecione **Fechar**.



## <a name="distribute-configuration-manager-packages"></a>Distribuir pacotes do Configuration Manager

Todos os pacotes devem ser distribuídos para os servidores que tiverem sido atribuídos a função de ponto de distribuição na hierarquia do Configuration Manager. Siga as instruções abaixo para iniciar a distribuição de pacote.

1.  Distribua os pacotes de software.

    1.  No console do Configuration Manager, vá para **A biblioteca de Software** \> **Gerenciamento de aplicativos** \> **pacotes**. Selecione todos os pacotes de software que você deseja distribuir e selecione **Distribuir conteúdo**.

    2.  Revise a lista de pacotes e selecione **Avançar**.

    3.  Adicione todos os servidores de ponto de distribuição (ou grupos de ponto de distribuição, dependendo de sua hierarquia do Configuration Manager) à lista e selecione **Avançar**.

    4.  Selecione **Avançar**e, em seguida, selecione **Fechar**.

2.  Distribua os pacotes de driver.

    1.  No console do Configuration Manager, vá para **A biblioteca de Software** \> **sistemas operacionais** \> **Pacotes de Driver**. Selecione todos os pacotes de driver que você deseja distribuir e selecione **Distribuir conteúdo**.

    2.  Revise a lista de pacotes e selecione **Avançar**.

    3.  Adicione todos os servidores de ponto de distribuição (ou grupos de ponto de distribuição, dependendo de sua hierarquia do Configuration Manager) à lista e selecione **Avançar**.

    4.  Selecione **Avançar**e, em seguida, selecione **Fechar**.

3.  Distribua os pacotes do sistema operacional.

    1.  No console do Configuration Manager, vá para **A biblioteca de Software** \> **sistemas operacionais** \> **Imagens do sistema operacional**. Selecione todas as imagens de sistema operacional que você deseja distribuir e selecione **Distribuir conteúdo**.

    2.  Revise a lista de pacotes e selecione **Avançar**.

    3.  Adicione todos os servidores de ponto de distribuição (ou grupos de ponto de distribuição, dependendo de sua hierarquia do Configuration Manager) à lista e selecione **Avançar**.

    4.  Selecione **Avançar**e, em seguida, selecione **Fechar**.

> [!NOTE]
> Distribuição de pacote pode levar algum tempo, dependendo do tamanho do pacote, hierarquia do Configuration Manager, número de servidores de ponto de distribuição e a largura de banda disponível em sua rede.
> 
> Todos os pacotes devem ser distribuídos antes de começar a implantação de uma unidade de salas de equipes da Microsoft.
> 
> Você pode examinar o status da sua distribuição de pacote no console do Configuration Manager indo para **monitoramento** \> **Status de distribuição** \> **Status do conteúdo**.

## <a name="configuration-manager-task-sequences"></a>Sequências de tarefas do Configuration Manager

Use sequências de tarefas com o System Center Configuration Manager para automatizar as etapas de implantação de uma imagem do sistema operacional em um computador de destino. Para implantar uma unidade de salas de equipes da Microsoft de forma automática, você cria uma sequência de tarefa que faz referência a imagem de inicialização usada para iniciar o computador de destino de salas de equipes da Microsoft, a imagem do sistema operacional Windows 10 Enterprise que você deseja instalar e qualquer outro conteúdo adicional, como outros aplicativos ou atualizações de software.

### <a name="import-the-sample-task-sequence"></a>Importar a sequência de tarefas de amostra

Você pode baixar e facilmente importar uma sequência de tarefas de amostra e personalizá-lo para atender às suas necessidades.

1.  [**Baixe**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) a sequência de tarefas de amostra e copiar o arquivo zip baixado em um local compartilhado.
2.  No console do Configuration Manager, vá para **A biblioteca de Software** \> **sistemas operacionais** \> **Sequências de tarefas**e, em seguida, selecione **Importar sequência de tarefa**.

3.  Selecione **navegar**, vá para o local de pasta compartilhada que você usou na etapa 1, selecione o arquivo **. zip de implantação do Microsoft equipes salas (EN-US)** e selecione **Avançar**.

4.  Definir a **ação** para **Criar novo**e selecione **Avançar**.

5.  Confirme as configurações e selecione **Avançar**.

6.  Selecione **Fechar**.

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a>Valide que os pacotes de referência corretamente vinculados a cada etapa de sequência de tarefa.

1. Selecione a sequência de tarefa importada e selecione **Editar**.

    O Editor de sequência de tarefas abre e exibe cada etapa sequencial que você precisa para implantar e configurar uma unidade de salas de equipes da Microsoft.

2. Percorrer cada etapa e preencha as atualizações recomendadas:

   1. **Reinicie o Windows PE**: esta etapa é reiniciado e carrega o computador Windows PXE. Nenhuma alteração é necessária para esta etapa.

   2. **Partição de disco 0 – UEFI**: esta etapa apaga a configuração do disco e cria partições com base em configurações definidas. Recomendamos que você não faça alterações para esta etapa.

   3. **Definir nome do computador SRS**: esta etapa inclui um aplicativo de HTML para fornecer uma interface do usuário para definir um nome de computador para a unidade de salas de equipes da Microsoft durante a implantação.
      -  Esta é uma etapa opcional, mas ele pode ser desabilitado apenas se você quiser gerenciar por meio de um processo alternativo de nomeação do computador.
      -  Verifique se o pacote **SRS v2 - Set-SRSComputerName** é selecionado. Se não for, navegue até o pacote e selecioná-la.

   4. **Aplicar o sistema de operacional**: esta etapa Especifica a imagem do sistema operacional a serem implantados e o arquivo de resposta Sysprep autônoma usar.
      -  Verifique se o arquivo de imagem de sistema operacional Windows 10 Enterprise correto está selecionado.
      -  Verifique se **usar uma autônoma ou Sysprep o arquivo de resposta para uma instalação personalizada** está habilitado, e o **SRS v2 - pacote Sysprep** está selecionada. Além disso, certifique-se de que o **Nome de arquivo** está definido como **Unattend. XML**.

   5. **Aplicar configurações do Windows**: esta etapa reúne informações sobre a instalação do Windows.
      -  Fornecer informações de registro e de licenciamento, incluindo a chave do produto, senha da conta de administrador local e fuso horário (dependendo das suas necessidades).

   6. **Aplicar configurações de rede**: esta etapa permite especificar um grupo de trabalho ou o nome de domínio do Active Directory e a unidade organizacional.
      > [!NOTE]
      > Consulte o [domínio do sistema de sala Skype ingressando considerações](domain-joining-considerations.md) para ações recomendadas que você precisa para implantar as unidades de salas de equipes da Microsoft como membros de um domínio Actve Directory.
   7. **Aplicar Drivers:** Esta etapa e seus subetapas são usadas para implantar baseada no modelo do Surface Pro, que você tem de firmware e drivers de dispositivo aplicáveis. Atualize cada etapa para especificar o pacote de driver relevantes associado com essa implantação.
      -   Cada pacote de driver é configurado para aproveitar os filtros Windows Management Instrumentation (WMI) para implantar drivers relevantes e firmware com base em o Surface Pro marca e modelo.
      -   É altamente recomendável que você não alterar a configuração desses drivers, caso contrário, a implantação pode falhar.

   8. **Configurar o Windows e o Configuration Manager**: esta etapa implanta e configura o cliente do Gerenciador de configuração. Atualize esta etapa para especificar o pacote de cliente interno do Configuration Manager.

   9. **Instalar o certificado de raiz**: esta etapa distribui o certificado raiz para dispositivos não – associados a um domínio e, portanto, é opcional, mas desabilitado por padrão.
      -   Habilite esta etapa se você precisa para implantar um certificado raiz para as unidades de salas de equipes da Microsoft.
      -   Se você precisar realizar esta etapa, verifique o **SRS v2 – pacote do certificado raiz** e o **redirecionamento de sistema de arquivo desabilitar 64 bits** são selecionados.

   10. **Instalar e configurar o agente de monitoração**: essa etapa instala a versão de 64 bits do agente do Microsoft Azure Monitor e configura o agente para se conectar ao seu espaço de trabalho de análise de Log.
       -   Esta etapa é desabilitada por padrão. Habilite esta etapa somente se você pretende usar o agente de monitoramento para monitorar a integridade de seus unidades de salas de equipes da Microsoft.
       -   Editar esta etapa e atualizar os parâmetros de linha de comando para especificar sua **ID de espaço de trabalho** e a **Chave do espaço de trabalho**.
       -   Consulte [Configure testar dispositivos para monitoramento do Windows Azure](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) para obter mais informações sobre como obter a ID de espaço de trabalho de pacote de gerenciamento de operações e a chave primária.
       -   Verifique se o **redirecionamento de sistema de arquivo desabilitar 64 bits** e **SRS v2 – pacote de agente de monitoramento do Microsoft** estão marcada.
       -   Para obter mais informações sobre como monitorar a integridade da sua implantação de salas de equipes da Microsoft, consulte [gerenciamento de planejar salas de equipes da Microsoft com o Azure Monitor](azure-monitor-plan.md), [gerenciamento de salas de equipes da Microsoft Deploy com o Azure Monitor](azure-monitor-deploy.md) e [Microsoft gerenciar As equipes de dispositivos de salas com Monitor do Azure](azure-monitor-manage.md).

   11. **Arquivos de configuração de v2 SRS de cópia**: esta etapa copia os arquivos de instalação e configuração necessários do kit de implantação do Microsoft equipes salas na unidade de disco rígido local. Sem personalização é necessária para esta etapa.
       -   Verifique se o **SRS v2 – SRS pacote de aplicativo** e o **redirecionamento de sistema de arquivo desabilitar 64 bits** são selecionado.

   12. **Install-SRSv2-atualizações de sistema operacional**: essa etapa implanta quaisquer atualizações de obrigatório do sistema operacional necessárias com a implantação de salas de equipes da Microsoft. Do the following:
       -   Verifique se [Configure um console de salas de equipes da Microsoft](console.md) para ver quais atualizações são necessárias.
       -   Verifique se seu **SRS v2 – pacote de atualizações do sistema operacional** inclui todas as atualizações necessárias.
       -   Verifique se o **SRS v2 – pacote de atualizações do sistema operacional** está selecionado.
       -   Verifique se a diretiva de execução do PowerShell é definida para **desvio**.

   13. **Reiniciar o computador**: esta etapa reinicializa o computador depois que as atualizações obrigatórias de sistema operacional estão instaladas. Sem personalização é necessária para esta etapa.

   14. **Configurar componentes do Windows**: esta etapa configura os recursos necessários do Windows. Sem personalização é necessária para esta etapa.

   15. **Reiniciar o computador**: esta etapa reinicializa o computador depois que os recursos do Windows são configurados. Sem personalização é necessária para esta etapa.

   16. **Adicionar usuário Local do Skype**: essa etapa cria a conta do Skype local usada para entrar no Windows e inicie o aplicativo Microsoft equipes salas automaticamente. Esta etapa não tem nenhum pacote de software associado a ela, e sem personalização é necessária para ele.

   17. **Definido para cima e para configurar o aplicativo de SRS**: esta etapa configura a instalação do aplicativo de salas de equipes da Microsoft para a próxima inicialização do sistema operacional.
       -   Verifique se que o **redirecionamento de sistema de arquivo desabilitar 64 bits** e **SRS v2 – configurar pacote de instalação do SRS** estão selecionadas.

> [!IMPORTANT]
> É muito importante que as etapas de sequência de tarefa devem ser na ordem fornecida. Modificar a ordem das etapas ou etapas adicionais de configuração pode interromper a implantação.
>
> **Definido para cima e para configurar o aplicativo de SRS** etapa deve ser a última etapa na sequência de tarefas, caso contrário, a implantação pode falhar.

### <a name="create-deployment-for-the-task-sequence"></a>Criar a implantação da sequência de tarefas

1. Selecione a sequência de tarefas e selecione **implantar**.

2. Selecione **Procurar** para selecionar o conjunto de destino para implantação.

3. Selecione **Todos os computadores desconhecido** e selecione **Okey**.

4. Selecione **Avançar**.

5. Selecione **disponível** na lista suspensa **finalidade** .

6. Selecione **apenas a mídia e PXE** na lista **disponibilizar o seguinte** e selecione **Avançar**.
   > [!WARNING]
   > É muito importante que o **objetivo** é definido como **disponível**. Certifique-se de que o **objetivo** é **não** definido como **obrigatório**. Também Certifique-se de que você selecione **apenas a mídia e PXE** nos **tornar disponível para o seguinte**.
   >
   > Configurar esses valores para algo diferente pode fazer com que todos os computadores obter a imagem de implantação do Microsoft equipes salas quando inicializado.
7. Não especifique qualquer agenda e selecione **Avançar**.

8. Não altere qualquer coisa dentro da seção **Experiência do usuário** e selecione **Avançar**.

9. Não altere qualquer coisa dentro da seção de **alertas** e selecione **Avançar**.

10. Não altere qualquer coisa dentro da seção de **Pontos de distribuição** e selecione **Avançar**.

11. Confirme as configurações e selecione **Avançar**.

12. Selecione **Fechar**.

<a name="validate-and-troubleshoot-the-solution"></a>Validar e solucionar problemas da solução
--------------------------------------

Depois de concluir as sequências de tarefas do System Center Configuration Manager, você precisará executar um teste para validar que a sequência de tarefa pode implantar e configurar unidades de salas de equipes da Microsoft.

1.  Conecte o dispositivo de teste à rede com fio, usando um dos adaptadores Ethernet suportados ou usando a superfície encaixe. Se a funcionalidade de inicialização PXE não tiver sido configurada para o seu ambiente, você pode usar a imagem de inicialização no USB unidade flash [que você criou anteriormente](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) para inicializar a partir do USB e conecte-se ao Gerenciador de configuração.

2.  Acessar o firmware e iniciar os inicialização PXE:

    1.  Certifique-se de que o dispositivo de superfície é desligado.

    2.  Pressione e mantenha pressionado o botão de **Volume para cima** .

    3.  Pressione e solte o botão de **energia** .

    4.  Após o dispositivo começa a inicialização, solte o botão de **Volume para cima** .

    5.  Selecione a **configuração de inicialização**.

    6.  Siga um destes procedimentos:

        -   Selecione **inicialização PXE**e arraste-o para o topo da lista. Como alternativa, você poderá passar esquerda no adaptador de rede para inicializar o dispositivo imediatamente. Isso não afetará a ordem de inicialização.
        -   Selecione a unidade flash USB que contém a mídia de inicialização.

3.  Selecione **Sair**e, em seguida, selecione **Reiniciar agora**.

4.  Quando solicitado, selecione **Enter** para serviço de inicialização de rede.

5.  Windows PE carregará na memória e iniciará o Assistente de sequência de tarefa. Selecione **Avançar** para continuar.

6.  Selecione a sequência de tarefas que você importou anteriormente e selecione **Avançar**.

7.  Depois que a configuração de disco for aplicada, você será solicitado que especifique um nome de computador para o dispositivo. A interface do usuário exibirá o nome de um computador recomendada com base no número de série do dispositivo Surface Pro. Você pode aceitar o nome proposto ou especifique um novo. Siga as instruções na tela de atribuição de nome do computador. Quando você selecionar **Aceitar**, começa a implantação.

8.  O restante do processo de implantação é automático e não pede qualquer entrada do usuário mais.

9.  Depois que a sequência de tarefas de implantação estiver concluída, configurando o dispositivo, você verá a tela configuração a seguir que solicita a definir as configurações de aplicativo de salas de equipes da Microsoft.

    ![Tela de instalação inicial para o aplicativo de salas de equipes da Microsoft](../media/room-systems-scale-image2.png)

10.  Conecte o Surface Pro no console do Microsoft equipes salas e definir as configurações de aplicativo.

11.  Valide se os recursos listados na [Ajuda do Microsoft equipes salas](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) estão funcionando no dispositivo implantado.


Para solucionar problemas de uma falha na instalação, verifique o arquivo **SMSTS** , que registra todas as etapas executadas em uma sequência de tarefas do Configuration Manager.

O arquivo SMSTS é armazenado em um dos vários caminhos, dependendo do estágio do processo de compilação. Verifique a tabela a seguir para identificar o caminho para o arquivo SMSTS.


| **Fase de implantação**                                                            | **Caminho de log de sequência de tarefa**                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| WinPE, antes de formato HDD                                                        | X:\\Windows\\Temp\\smstslog\\SMSTS             |
| WinPE, após o formato HDD                                                         | C:\\_SMSTaskSequence\\Logs\\Smstslog\\SMSTS    |
| Sistema operacional implantado, antes que o agente do Configuration Manager foi instalado | c:\\_SMSTaskSequence\\Logs\\Smstslog\\SMSTS    |
| Sistema operacional e o agente do Configuration Manager implantado                   | % windir %\\System32\\ccm\\logs\\Smstslog\\SMSTS |
| Execução de sequência de tarefa concluída                                                | % windir %\\System32\\ccm\\logs\\SMSTS           |

> [!TIP]
> Você pode selecionar **F8** a qualquer momento durante a sequência de tarefas para abrir um console de comando e, em seguida, obter acesso ao arquivo SMSTS.

Para solucionar problemas de inicialização PXE, verifique os dois arquivos de log no servidor do Gerenciador de configuração que são específicos para ações de PXE:

-   **Pxecontrol.log**, localizado no diretório de logs de instalação do Configuration Manager

-   **Smspxe.log**, localizado no diretório de logs do ponto de gerenciamento do Gerenciador de configuração (MP)

Para obter uma lista completa dos arquivos de log que você pode usar para solucionar ainda mais a sua instalação do Configuration Manager, consulte [arquivos de Log no System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).
