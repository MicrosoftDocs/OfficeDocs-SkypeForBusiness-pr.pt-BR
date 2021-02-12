---
title: Preparar o dispositivo do Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: Saiba como preparar o dispositivo do Cloud Connector para implantação e uso com o Sistema de Telefonia (Cloud PBX).
ms.openlocfilehash: 74c4885a25b4176f4d5eb3ac27926bd9528387c6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358937"
---
# <a name="prepare-your-cloud-connector-appliance"></a><span data-ttu-id="35cba-103">Preparar o dispositivo do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="35cba-103">Prepare your Cloud Connector appliance</span></span>

> [!Important]
> <span data-ttu-id="35cba-104">O Cloud Connector Edition será destivado em 31 de julho de 2021 junto com o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="35cba-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="35cba-105">Depois que sua organização tiver atualizado para o Teams, saiba como conectar sua rede de telefonia local ao Teams usando o [Roteamento Direto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="35cba-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="35cba-106">Saiba como preparar o dispositivo do Cloud Connector para implantação e uso com o Sistema de Telefonia (Cloud PBX).</span><span class="sxs-lookup"><span data-stu-id="35cba-106">Learn about how to prepare your Cloud Connector appliance for deployment and use with Phone System (Cloud PBX).</span></span>

<span data-ttu-id="35cba-107">Esta seção descreve como obter os arquivos de instalação do Skype for Business Cloud Connector Edition, instalar o software do Cloud Connector e preparar o dispositivo do Cloud Connector para implantação.</span><span class="sxs-lookup"><span data-stu-id="35cba-107">This section describes how to get the Skype for Business Cloud Connector Edition installation files, install Cloud Connector software, and prepare your Cloud Connector appliance for deployment.</span></span> <span data-ttu-id="35cba-108">Depois de concluir todas as etapas desta seção, você estará pronto para implantar o Cloud Connector para um único site ou vários sites.</span><span class="sxs-lookup"><span data-stu-id="35cba-108">After you have completed all steps in this section, you will be ready to deploy Cloud Connector for a single site or multiple sites.</span></span> <span data-ttu-id="35cba-109">Se você tiver uma implantação existente do Cloud Connector e ainda não tiver atualizado para o Cloud Connector versão 2.1, consulte Atualizar para uma nova versão [do Cloud Connector.](upgrade-to-a-new-version-of-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="35cba-109">If you have an existing Cloud Connector deployment, and you have not yet upgraded to Cloud Connector version 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>

> [!NOTE]
> <span data-ttu-id="35cba-110">A Microsoft dá suporte à versão atual do Cloud Connector Edition, versão 2.1.</span><span class="sxs-lookup"><span data-stu-id="35cba-110">Microsoft supports the current version of Cloud Connector Edition, version 2.1.</span></span> <span data-ttu-id="35cba-111">Se você configurou a atualização automática, o Cloud Connector será atualizado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="35cba-111">If you configured automatic update, Cloud Connector will update automatically.</span></span> <span data-ttu-id="35cba-112">Se você configurou a atualização manual, precisará atualizar para a versão 2.1 dentro de 60 dias de seu lançamento.</span><span class="sxs-lookup"><span data-stu-id="35cba-112">If you configured manual update, you will need to upgrade to version 2.1 within 60 days of its release.</span></span> <span data-ttu-id="35cba-113">A Microsoft dará suporte à versão anterior por 60 dias após o lançamento da versão 2.1 para permitir a atualização.</span><span class="sxs-lookup"><span data-stu-id="35cba-113">Microsoft will support the previous version for 60 days after the release of 2.1 to allow you time to upgrade.</span></span> 

> [!NOTE]
> <span data-ttu-id="35cba-114">Para a versão 2.1 e posterior do Cloud Connector, o dispositivo host deve ter o .NET Framework 4.6.1 ou posterior instalado.</span><span class="sxs-lookup"><span data-stu-id="35cba-114">For Cloud Connector version 2.1 and later, the host appliance must have .NET Framework 4.6.1 or later installed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="35cba-115">Para uma implantação bem-sucedida, quando você executar os cmdlets para configurar o Skype for Business Cloud Connector Edition, sempre use a mesma sessão de console que a que você iniciou.</span><span class="sxs-lookup"><span data-stu-id="35cba-115">For successful deployment, when you run the cmdlets to configure Skype for Business Cloud Connector Edition, always use the same console session as the one you started in.</span></span> <span data-ttu-id="35cba-116">Evite alternar para sessões diferentes durante a implantação e configuração.</span><span class="sxs-lookup"><span data-stu-id="35cba-116">Avoid switching to different sessions during the deployment and configuration.</span></span> 

> [!NOTE]
> <span data-ttu-id="35cba-117">Existem algumas etapas que você executa apenas para o primeiro dispositivo em sua implantação: criar um compartilhamento para o diretório de sites, baixar os bits e preparar um arquivo vhDX (disco rígido virtual) da imagem ISO do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="35cba-117">There are some steps that you perform only for the first appliance in your deployment: creating a share for the site directory, downloading the bits, and preparing a virtual hard disk (VHDX) file from the Windows Server ISO image.</span></span> 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a><span data-ttu-id="35cba-118">Baixar o instalador do Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="35cba-118">Download the Skype for Business Cloud Connector Edition installer</span></span>

1. <span data-ttu-id="35cba-119">No servidor host onde as VMs do Cloud Connector serão executados, baixe os arquivos de instalação: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .</span><span class="sxs-lookup"><span data-stu-id="35cba-119">On the host server where the Cloud Connector VMs will run, download the installation files: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="35cba-120">O servidor host deve ser capaz de acessar a Internet durante a instalação do Cloud Connector porque arquivos adicionais são baixados durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="35cba-120">The host server must be able to access the Internet during the installation of Cloud Connector because additional files are downloaded during the installation.</span></span> 

2. <span data-ttu-id="35cba-121">Execute o instalador e aceite os valores padrão durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="35cba-121">Run the installer and accept the default values during the installation.</span></span>

3. <span data-ttu-id="35cba-122">Confirme se a instalação foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="35cba-122">Confirm that the installation completed successfully.</span></span>

## <a name="verify-the-installation-and-configure-the-environment"></a><span data-ttu-id="35cba-123">Verificar a instalação e configurar o ambiente</span><span class="sxs-lookup"><span data-stu-id="35cba-123">Verify the installation and configure the environment</span></span>

1. <span data-ttu-id="35cba-124">Abra um console do PowerShell como administrador e confirme se os cmdlets do Skype for Business Cloud Connector Edition estão disponíveis usando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="35cba-124">Open a PowerShell console as administrator and confirm that the Skype for Business Cloud Connector Edition cmdlets are available using the following cmdlet:</span></span>

   ```powershell
   Get-Command *-Cc*
   ```

    <span data-ttu-id="35cba-125">O comando deve retornar uma lista de cmdlets para o Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="35cba-125">The command should return a list of cmdlets for Skype for Business Cloud Connector Edition.</span></span>

2. <span data-ttu-id="35cba-126">Os arquivos VHDs, SfBBits e VersionInfo serão armazenados no **Diretório de Sites.**</span><span class="sxs-lookup"><span data-stu-id="35cba-126">The VHDs, SfBBits, and VersionInfo files will be stored in the **Site Directory**.</span></span>

    <span data-ttu-id="35cba-127">Você pode encontrar o local do **Diretório de Sites** com o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="35cba-127">You can find the location of the **Site Directory** with the following cmdlet:</span></span>

   ```powershell
   Get-CcSiteDirectory
   ```

    <span data-ttu-id="35cba-128">O comando deve retornar um local em seu sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="35cba-128">The command should return a location in your file system.</span></span> <span data-ttu-id="35cba-129">O local pode ser uma pasta local ou um compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="35cba-129">The location can be a local folder or a file share.</span></span> <span data-ttu-id="35cba-130">O local padrão para o **Diretório de Sites** é: %USERPROFILE%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="35cba-130">The default location for the **Site Directory** is: %USERPROFILE%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="35cba-131">O local padrão deve ser alterado para um compartilhamento de arquivos no primeiro dispositivo criado em cada site.</span><span class="sxs-lookup"><span data-stu-id="35cba-131">The default location should be changed to a file share on the first appliance created in each site.</span></span>

    <span data-ttu-id="35cba-132">O local selecionado deve ser:</span><span class="sxs-lookup"><span data-stu-id="35cba-132">The location you select must be:</span></span>

   - <span data-ttu-id="35cba-133">Criado no primeiro dispositivo criado em cada site.</span><span class="sxs-lookup"><span data-stu-id="35cba-133">Created on the first appliance created in each site.</span></span>

   - <span data-ttu-id="35cba-134">Uma pasta compartilhada que pode ser acessada pelos outros servidores host (dispositivos) no mesmo site.</span><span class="sxs-lookup"><span data-stu-id="35cba-134">A shared folder that is accessible by the other host servers (appliances) in the same site.</span></span>

     <span data-ttu-id="35cba-135">Para definir o **Diretório de** Sites para um local diferente do padrão, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="35cba-135">To set the **Site Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    <span data-ttu-id="35cba-136">Se você estiver implantando alta disponibilidade (HA) para o site, execute o cmdlet para definir o Diretório de **Sites** para o mesmo local em cada servidor host dentro do site.</span><span class="sxs-lookup"><span data-stu-id="35cba-136">If you are deploying High Availability (HA) for the site, make sure you run the cmdlet to set the **Site Directory** to the same location on each host server within the site.</span></span>

    <span data-ttu-id="35cba-137">Ao fazer logon e implantar cada dispositivo no site, certifique-se de que sua conta de logon atual tenha o acesso certo ao **Diretório de Sites.**</span><span class="sxs-lookup"><span data-stu-id="35cba-137">When you log on and deploy each appliance in the site, make sure your current logon account has the right access to the **Site Directory**.</span></span>

3. <span data-ttu-id="35cba-138">O **Diretório de Dispositivos** é o diretório raiz de trabalho local do Skype for Business Cloud Connector Edition e o local onde certificados, instâncias e logs externos são salvos.</span><span class="sxs-lookup"><span data-stu-id="35cba-138">The **Appliance Directory** is the local working root directory for Skype for Business Cloud Connector Edition, and the location where external certificates, instances, and logs are saved.</span></span> <span data-ttu-id="35cba-139">O local padrão é: %USERPROFILE%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="35cba-139">The default location is: %USERPROFILE%\CloudConnector\ApplianceRoot.</span></span>

    <span data-ttu-id="35cba-140">Para localizar o Diretório de **Dispositivos,** execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="35cba-140">To find the location of the **Appliance Directory**, run the following cmdlet:</span></span>

   ```powershell
   Get-CcApplianceDirectory
   ```

    <span data-ttu-id="35cba-141">Para definir o **Diretório de** Dispositivos para um local diferente do padrão, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="35cba-141">To set the **Appliance Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    <span data-ttu-id="35cba-142">O Diretório de Dispositivos deve ser definido como uma pasta local no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="35cba-142">The Appliance Directory should be set to a local folder on the appliance.</span></span> <span data-ttu-id="35cba-143">Você só deve definir o **Diretório de Dispositivos** antes de iniciar a implantação do Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="35cba-143">You should only set the **Appliance Directory** before you start the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="35cba-144">Se você alterá-lo após a implantação, será necessário reimplantar o servidor host.</span><span class="sxs-lookup"><span data-stu-id="35cba-144">If you change it after deployment, you'll need to redeploy the host server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="35cba-145">O caminho para o **Diretório de Dispositivos** não deve conter espaços.</span><span class="sxs-lookup"><span data-stu-id="35cba-145">The path to the **Appliance Directory** must not contain any spaces.</span></span>

## <a name="set-the-path-for-the-external-edge-certificate"></a><span data-ttu-id="35cba-146">Definir o caminho para o certificado de Borda externo</span><span class="sxs-lookup"><span data-stu-id="35cba-146">Set the path for the external Edge certificate</span></span>

- <span data-ttu-id="35cba-147">Execute o cmdlet a seguir para definir o caminho, incluindo o nome do arquivo, para o certificado de Borda externo.</span><span class="sxs-lookup"><span data-stu-id="35cba-147">Run the following cmdlet to set the path, including the file name, to the external Edge certificate.</span></span> <span data-ttu-id="35cba-148">Por exemplo: C:\certs\cce\ap.contoso.com.pfx.</span><span class="sxs-lookup"><span data-stu-id="35cba-148">For example: C:\certs\cce\ap.contoso.com.pfx.</span></span> <span data-ttu-id="35cba-149">O certificado deve conter chaves privadas.</span><span class="sxs-lookup"><span data-stu-id="35cba-149">The certificate must contain private keys.</span></span>

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > <span data-ttu-id="35cba-150">Observe que o parâmetro -Target é específico das versões 1.4.2 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="35cba-150">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

    <span data-ttu-id="35cba-151">Especifique o caminho completo para o certificado externo, incluindo o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="35cba-151">Specify the full path to the external certificate, including the file name.</span></span> <span data-ttu-id="35cba-152">O certificado pode ser armazenado localmente ou em um compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="35cba-152">The certificate can be stored locally or on a file share.</span></span> <span data-ttu-id="35cba-153">Se o certificado estiver armazenado em uma pasta compartilhada, a pasta compartilhada deverá ser criada no primeiro dispositivo de cada site e deverá ser acessível por outros dispositivos pertencentes ao mesmo site.</span><span class="sxs-lookup"><span data-stu-id="35cba-153">If the certificate is stored in a shared folder, the shared folder must be created on the first appliance of each site and must be accessible by other appliances belonging to the same site.</span></span> <span data-ttu-id="35cba-154">Este cmdlet copia o certificado externo para o **Diretório de Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="35cba-154">This cmdlet copies the external certificate to the **Appliance Directory**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="35cba-155">Se você tiver atualizado para o Cloud Connector versão **1.4.2** ou posterior, certifique-se de que seu certificado externo preparado contenha chaves privadas e a cadeia completa de certificados, incluindo o certificado ca raiz e os certificados ca intermediários.</span><span class="sxs-lookup"><span data-stu-id="35cba-155">**If you have updated to Cloud Connector version 1.4.2 or later**, make sure your prepared external certificate contains private keys and the full certificate chain including the root CA certificate and the intermediate CA certificates.</span></span> <span data-ttu-id="35cba-156">Se você AINDA NÃO tiver atualizado para o Cloud Connector versão **1.4.2,** certifique-se de que seu certificado externo preparado contenha chaves privadas.</span><span class="sxs-lookup"><span data-stu-id="35cba-156">**If you have NOT yet updated to Cloud Connector version 1.4.2**, make sure your prepared external certificate contains private keys.</span></span> <span data-ttu-id="35cba-157">Esse certificado externo deve ser emitido por uma Autoridade de Certificação confiável para o Windows por padrão.</span><span class="sxs-lookup"><span data-stu-id="35cba-157">This external certificate must be issued by a Certificate Authority that is trusted by Windows by default.</span></span>

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a><span data-ttu-id="35cba-158">Definir o caminho para o gateway PSTN externo/certificado SBC</span><span class="sxs-lookup"><span data-stu-id="35cba-158">Set the path for the external PSTN gateway/SBC certificate</span></span>

<span data-ttu-id="35cba-159">Se você estiver usando o TLS entre o Servidor de Mediação e o gateway PSTN/SBC, execute o cmdlet a seguir para definir o caminho, incluindo o nome do arquivo, para o certificado de gateway.</span><span class="sxs-lookup"><span data-stu-id="35cba-159">If you are using TLS between the Mediation Server and the PSTN gateway/SBC, run the following cmdlet to set the path, including the file name, to the gateway certificate.</span></span> <span data-ttu-id="35cba-160">Por exemplo: C:\certs\cce\sbc.contoso.com.cer.</span><span class="sxs-lookup"><span data-stu-id="35cba-160">For example: C:\certs\cce\sbc.contoso.com.cer.</span></span> <span data-ttu-id="35cba-161">O certificado deve conter a CA raiz e a cadeia intermediária do certificado atribuído ao gateway:</span><span class="sxs-lookup"><span data-stu-id="35cba-161">The certificate must contain the root CA and the intermediate chain for the certificate assigned to the gateway:</span></span>

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> <span data-ttu-id="35cba-162">Observe que o parâmetro -Target é específico das versões 1.4.2 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="35cba-162">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

## <a name="create-virtual-switches-in-hyper-v-manager"></a><span data-ttu-id="35cba-163">Criar comutadores virtuais no Gerenciador do Hyper-V</span><span class="sxs-lookup"><span data-stu-id="35cba-163">Create virtual switches in Hyper-V Manager</span></span>

1. <span data-ttu-id="35cba-164">Abra **o Gerenciador de Comutor** Virtual do Gerenciador do Hyper-V e selecione Novo Gerenciador de  >   **Comutor Virtual.**</span><span class="sxs-lookup"><span data-stu-id="35cba-164">Open **Hyper-V Manager** > **Virtual Switch Manager**, and select **New Virtual Switch Manager**.</span></span>

2. <span data-ttu-id="35cba-165">Crie um comuporte virtual externo e a bind-o ao adaptador de rede física que está conectado ao seu domínio de rede interno:</span><span class="sxs-lookup"><span data-stu-id="35cba-165">Create an External virtual switch and bind it to the physical network adapter that is connected to your internal network domain:</span></span>

    <span data-ttu-id="35cba-166">Selecione **Permitir que o sistema operacional de gerenciamento compartilhe esse adaptador de rede** para esse comutor virtual.</span><span class="sxs-lookup"><span data-stu-id="35cba-166">Select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

3. <span data-ttu-id="35cba-167">Crie um comuporte virtual externo e a bind-o ao adaptador de rede física que é roteado para a Internet:</span><span class="sxs-lookup"><span data-stu-id="35cba-167">Create an External virtual switch and bind it to the physical network adapter that is routed to the Internet:</span></span>

    <span data-ttu-id="35cba-168">Desleixar **Permitir que o sistema operacional de gerenciamento compartilhe esse adaptador de rede** para esse comutor virtual.</span><span class="sxs-lookup"><span data-stu-id="35cba-168">De-select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

4. <span data-ttu-id="35cba-169">De definir o nome do comutadores que conecta sua rede de perímetro ao seu domínio de rede interno **SfB CCE Corpnet Switch**.</span><span class="sxs-lookup"><span data-stu-id="35cba-169">Set the name of the switch that connects your perimeter network to your internal network domain **SfB CCE Corpnet Switch**.</span></span>

    <span data-ttu-id="35cba-170">De definir o nome do comutadores que conecta sua rede de perímetro ao Comutadores de **Internet CCE CCE do SfB da Internet da Internet.**</span><span class="sxs-lookup"><span data-stu-id="35cba-170">Set the name of the switch that connects your perimeter network to the Internet **SfB CCE Internet Switch**.</span></span>

## <a name="update-the-cloudconnectorini-configuration-file"></a><span data-ttu-id="35cba-171">Atualizar o arquivo CloudConnector.ini configuração</span><span class="sxs-lookup"><span data-stu-id="35cba-171">Update the CloudConnector.ini configuration file</span></span>

<span data-ttu-id="35cba-172">Prepare o CloudConnector.ini usando as informações coletadas no tópico Determinar [parâmetros](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) de implantação no [tópico Plan for Skype for Business Cloud Connector Edition.](plan-skype-for-business-cloud-connector-edition.md)</span><span class="sxs-lookup"><span data-stu-id="35cba-172">Prepare the CloudConnector.ini file using the information you gathered in [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) in the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span>

<span data-ttu-id="35cba-173">Para atualizar o arquivo, primeiro execute o cmdlet a seguir para obter o modelo de exemplo (CloudConnector.Sample.ini):</span><span class="sxs-lookup"><span data-stu-id="35cba-173">To update the file, first run the following cmdlet to get the sample template (CloudConnector.Sample.ini):</span></span>

```powershell
Export-CcConfigurationSampleFile
```

<span data-ttu-id="35cba-174">O modelo de exemplo é armazenado no **Diretório de Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="35cba-174">The sample template is stored in the **Appliance Directory**.</span></span>

<span data-ttu-id="35cba-175">Depois de atualizá-lo com os valores do seu ambiente, salve o arquivo como CloudConnector.ini no **Diretório de Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="35cba-175">After you update it with the values for your environment, save the file as CloudConnector.ini in the **Appliance Directory**.</span></span> <span data-ttu-id="35cba-176">Você pode executar **Get-CcApplianceDirectory** para determinar o caminho para o **Diretório de Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="35cba-176">You can run **Get-CcApplianceDirectory** to determine the path to the **Appliance Directory**.</span></span>

<span data-ttu-id="35cba-177">Ao atualizar o arquivo .ini, considere o seguinte:</span><span class="sxs-lookup"><span data-stu-id="35cba-177">When updating the .ini file, consider the following:</span></span>

> [!NOTE]
> <span data-ttu-id="35cba-178">Nem todos os valores para o arquivo .ini são discutidos nesta seção, apenas aqueles com uma consideração especial são abordados aqui.</span><span class="sxs-lookup"><span data-stu-id="35cba-178">Not all values for the .ini file are discussed in this section, only those with a special consideration are covered here.</span></span> <span data-ttu-id="35cba-179">Para uma lista completa, consulte a [seção Determinar parâmetros de](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) implantação do tópico Plan for Skype for Business Cloud Connector [Edition.](plan-skype-for-business-cloud-connector-edition.md)</span><span class="sxs-lookup"><span data-stu-id="35cba-179">For a full list, see the [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) section of the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span> <span data-ttu-id="35cba-180">Para obter mais informações sobre quais valores precisam ser alterados para dispositivos adicionais ou novos sites, consulte Site único com alta disponibilidade [(HA)](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) em comparação com implantações de vários sites no tópico Implantar vários sites no [Cloud Connector.](deploy-multiple-sites-in-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="35cba-180">For more information about what values need to be changed for additional appliances or new sites, see [Single site with High Availability (HA) compared to multi-site deployments](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) in the topic [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 

- <span data-ttu-id="35cba-181">**SiteName:** O valor padrão é **Site1**.</span><span class="sxs-lookup"><span data-stu-id="35cba-181">**SiteName:** The default value is **Site1**.</span></span> <span data-ttu-id="35cba-182">Você deve atualizá-lo antes de implantar o Cloud Connector, porque quando você executar **Register-CcAppliance** para registrar um dispositivo em um site novo ou existente, o cmdlet usará **SiteName** para determinar qual site registrar.</span><span class="sxs-lookup"><span data-stu-id="35cba-182">You must update it before you deploy Cloud Connector, because when you run **Register-CcAppliance** to register an appliance to an existing or new site, the cmdlet will use **SiteName** to determine which site to register.</span></span>

     <span data-ttu-id="35cba-183">Se você deseja registrar o dispositivo em um novo site, o valor de **SiteName** deve ser exclusivo e diferente dos sites existentes.</span><span class="sxs-lookup"><span data-stu-id="35cba-183">If you want to register the appliance to a new site, the value of **SiteName** must be unique and different from existing sites.</span></span> <span data-ttu-id="35cba-184">Se você deseja registrar o dispositivo em um site existente, o valor de **SiteName** no arquivo .ini deve corresponder ao nome definido na configuração da organização do Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="35cba-184">If you want to register the appliance to an existing site, the value for **SiteName** in .ini file must match the name defined in your Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="35cba-185">Se você estiver copiando um arquivo de configuração de um site para outro, atualize o valor de **SiteName** para cada site de acordo.</span><span class="sxs-lookup"><span data-stu-id="35cba-185">If you are copying a configuration file from one site to another, make sure you update the value for **SiteName** for each site accordingly.</span></span>

- <span data-ttu-id="35cba-186">**ServerName:** O nome do servidor não deve conter o nome de domínio e deve ser limitado a 15 caracteres.</span><span class="sxs-lookup"><span data-stu-id="35cba-186">**ServerName:** The server name should not contain the domain name and should be limited to 15 characters.</span></span>

- <span data-ttu-id="35cba-187">**HardwareType:** Se você não definir ou deixar o valor como nulo, o valor padrão **normal** será usado.</span><span class="sxs-lookup"><span data-stu-id="35cba-187">**HardwareType:** If you don't set or leave the value to null, the default value of **Normal** will be used.</span></span> <span data-ttu-id="35cba-188">Use **o Normal** se você planeja implantar a versão maior do Cloud Connector para dar suporte a 500 chamadas simultâneas por máquina host, conforme descrito em Plan for Skype for Business Cloud Connector [Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="35cba-188">Use **Normal** if you plan to deploy the larger version of Cloud Connector to support 500 simultaneous calls per host machine as described in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> <span data-ttu-id="35cba-189">Use **o Mínimo** para uma implantação menor que suporte 50 chamadas simultâneas.</span><span class="sxs-lookup"><span data-stu-id="35cba-189">Use **Minimum** for a smaller deployment that supports 50 simultaneous calls.</span></span>

- <span data-ttu-id="35cba-190">**Comutadores virtuais Internet/Corpnet/Management:**: adicione o nome dos comutadores virtuais que você criou.</span><span class="sxs-lookup"><span data-stu-id="35cba-190">**Internet/Corpnet/Management virtual switches:**: Add the name of the virtual switches you have created.</span></span> <span data-ttu-id="35cba-191">Para o com switch virtual de gerenciamento, deixe o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="35cba-191">For the management virtual switch, leave the default value.</span></span> <span data-ttu-id="35cba-192">O script de implantação criará o comutar virtual de gerenciamento no início da implantação e o excluirá quando a implantação terminar.</span><span class="sxs-lookup"><span data-stu-id="35cba-192">The deployment script will create the management virtual switch at the beginning of deployment and delete it when the deployment finishes.</span></span>

- <span data-ttu-id="35cba-193">**ManagementIPPrefix:** ManagementIPPrefix na seção Rede deve ser uma sub-rede diferente de outros IPs internos.</span><span class="sxs-lookup"><span data-stu-id="35cba-193">**ManagementIPPrefix:** ManagementIPPrefix in the Network section must be a different subnet from other internal IPs.</span></span> <span data-ttu-id="35cba-194">Por exemplo, como mostra o valor padrão, ManagementIPPrefix é 192.168.213.0, enquanto AD IPAddress é 192.168.0.238.</span><span class="sxs-lookup"><span data-stu-id="35cba-194">For example, as the default value shows, ManagementIPPrefix is 192.168.213.0, while AD IPAddress is 192.168.0.238.</span></span>

    <span data-ttu-id="35cba-195">Os scripts de implantação criam um adaptador de rede de gerenciamento em cada máquina virtual, atribuem um IP de gerenciamento e o conectam a um com switch virtual de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="35cba-195">The deployment scripts create a management network adapter on each virtual machine, assign a management IP, and connect it to a management virtual switch.</span></span> <span data-ttu-id="35cba-196">Isso permite que o servidor host se conecte e gerencie cada máquina virtual por meio dessa rede de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="35cba-196">This enables the host server to connect to and manage each virtual machine via this management network.</span></span> <span data-ttu-id="35cba-197">O comutado virtual de gerenciamento é excluído quando a implantação é concluída.</span><span class="sxs-lookup"><span data-stu-id="35cba-197">The management virtual switch is deleted when the deployment is finished.</span></span>

- <span data-ttu-id="35cba-198">**Configurações específicas da VM base:** As configurações nesta seção devem ser configuradas para o cmdlet **Convert-CcIsoToVhdx.**</span><span class="sxs-lookup"><span data-stu-id="35cba-198">**Base VM specific configurations:** Settings in this section must be configured for the **Convert-CcIsoToVhdx** cmdlet.</span></span>

    <span data-ttu-id="35cba-199">Durante a preparação da imagem da VM base, a VM base será conectada ao com switch de rede interno.</span><span class="sxs-lookup"><span data-stu-id="35cba-199">During base VM image preparation, the base VM will be connected to the internal network switch.</span></span> <span data-ttu-id="35cba-200">As configurações a seguir são essenciais para que a VM possa acessar a Internet:</span><span class="sxs-lookup"><span data-stu-id="35cba-200">The following settings are critical for the VM to be able to access the Internet:</span></span>

  - <span data-ttu-id="35cba-201">[Comum] BaseVMIP: o endereço IP corpnet a ser atribuído à VM base.</span><span class="sxs-lookup"><span data-stu-id="35cba-201">[Common]BaseVMIP: the corpnet IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="35cba-202">[Rede] CorpnetDefaultGateway: o gateway padrão a ser atribuído à VM base.</span><span class="sxs-lookup"><span data-stu-id="35cba-202">[Network]CorpnetDefaultGateway: the default gateway to be assigned to the base VM.</span></span>

  - <span data-ttu-id="35cba-203">[Rede] CorpnetDNSIPAddress: o endereço IP DNS a ser atribuído à VM base.</span><span class="sxs-lookup"><span data-stu-id="35cba-203">[Network]CorpnetDNSIPAddress: the DNS IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="35cba-204">[Rede] WSUSServer: o endereço IP do Windows Server Update Service.</span><span class="sxs-lookup"><span data-stu-id="35cba-204">[Network]WSUSServer: the IP address of Windows Server Update Service.</span></span>

  - <span data-ttu-id="35cba-205">[Rede] WSUSStatusServer: o endereço IP do servidor de status do Serviço de Atualização do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="35cba-205">[Network]WSUSStatusServer: the IP address of Windows Server Update Service status server.</span></span>

  - <span data-ttu-id="35cba-206">[Rede] EnableReferSupport: isso definirá se o suporte a SIP REFER está habilitado ou desabilitado na Configuração de Tronco para seu IP/PBX.</span><span class="sxs-lookup"><span data-stu-id="35cba-206">[Network]EnableReferSupport: this will define whether SIP REFER support is enabled or disabled on the Trunk Configuration to your IP/PBX.</span></span>

- <span data-ttu-id="35cba-207">**IPs internos:**</span><span class="sxs-lookup"><span data-stu-id="35cba-207">**Internal IPs:**</span></span>

  - <span data-ttu-id="35cba-208">Certifique-se de que a máscara de sub-rede CorpnetIPPrefixLength está correta.</span><span class="sxs-lookup"><span data-stu-id="35cba-208">Make sure subnet mask CorpnetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="35cba-209">Certifique-se de que não haja conflitos de IP para esses IPs internos.</span><span class="sxs-lookup"><span data-stu-id="35cba-209">Make sure there are no IP conflicts for these internal IPs.</span></span>

- <span data-ttu-id="35cba-210">**IPs externos:**</span><span class="sxs-lookup"><span data-stu-id="35cba-210">**External IPs:**</span></span>

  - <span data-ttu-id="35cba-211">Para IP público de MR: especifique ExternalMRIPs para não NAT ou ExternalMRPublicIPs para NAT.</span><span class="sxs-lookup"><span data-stu-id="35cba-211">For MR public IP: specify either ExternalMRIPs for non-NAT or ExternalMRPublicIPs for NAT.</span></span>

  - <span data-ttu-id="35cba-212">ExternalSIPIPs e ExternalMRIPs podem ser os mesmos.</span><span class="sxs-lookup"><span data-stu-id="35cba-212">ExternalSIPIPs and ExternalMRIPs can be the same.</span></span>

  - <span data-ttu-id="35cba-213">Certifique-se de que a máscara de sub-rede InternetIPPrefixLength está correta.</span><span class="sxs-lookup"><span data-stu-id="35cba-213">Make sure subnet mask InternetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="35cba-214">Certifique-se de que não haja conflitos de IP para esses IPs externos.</span><span class="sxs-lookup"><span data-stu-id="35cba-214">Make sure there are no IP conflicts for these external IPs.</span></span>

- <span data-ttu-id="35cba-215">**Gateways:**</span><span class="sxs-lookup"><span data-stu-id="35cba-215">**Gateways:**</span></span>

  - <span data-ttu-id="35cba-216">Se você tiver apenas um gateway, remova a seção do gateway secundário.</span><span class="sxs-lookup"><span data-stu-id="35cba-216">If you have only one gateway, remove the section for the secondary gateway.</span></span> <span data-ttu-id="35cba-217">Se você tiver mais de dois gateways, crie seções adicionais copiando e copiando a existente e atualizando-a.</span><span class="sxs-lookup"><span data-stu-id="35cba-217">If you have more than two gateways, create additional sections by copying and pasting the existing one and then updating it.</span></span>

  - <span data-ttu-id="35cba-218">Certifique-se de que o endereço IP e a porta dos gateways estão corretos.</span><span class="sxs-lookup"><span data-stu-id="35cba-218">Make sure that the IP address and port of the gateway(s) are correct.</span></span>

  - <span data-ttu-id="35cba-219">Para dar suporte ao nível de HA do gateway PSTN, saia do gateway secundário e adicione os gateways adicionais que você usará.</span><span class="sxs-lookup"><span data-stu-id="35cba-219">To support PSTN gateway level HA, leave the secondary gateway, and add any additional gateways you will use.</span></span> <span data-ttu-id="35cba-220">Você pode copiar e colar uma entrada existente e atualizá-la.</span><span class="sxs-lookup"><span data-stu-id="35cba-220">You can copy and paste an existing entry and then update it.</span></span>

- <span data-ttu-id="35cba-221">Opcionalmente, você pode atualizar o valor LocalRoute para restringir os números de chamada de saída.</span><span class="sxs-lookup"><span data-stu-id="35cba-221">Optionally, you can update the LocalRoute value to restrict outbound call numbers.</span></span>

## <a name="download-the-bits-to-the-site-directory"></a><span data-ttu-id="35cba-222">Baixar os bits para o Diretório de Sites</span><span class="sxs-lookup"><span data-stu-id="35cba-222">Download the bits to the Site Directory</span></span>

<span data-ttu-id="35cba-223">Execute o seguinte cmdlet para baixar os arquivos de informações de bits e versões para o **Diretório de Sites:**</span><span class="sxs-lookup"><span data-stu-id="35cba-223">Run the following cmdlet to download the bits and version information files to the **Site Directory**:</span></span>

```powershell
Start-CcDownload
```

> [!NOTE]
> <span data-ttu-id="35cba-224">Você precisa executar esta etapa apenas para o primeiro dispositivo.</span><span class="sxs-lookup"><span data-stu-id="35cba-224">You need to perform this step for the first appliance only.</span></span> 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a><span data-ttu-id="35cba-225">Preparar o disco virtual base (VHDX) do arquivo ISO baixado</span><span class="sxs-lookup"><span data-stu-id="35cba-225">Prepare base virtual disk (VHDX) from the downloaded ISO file</span></span>

<span data-ttu-id="35cba-226">Esta etapa prepara um arquivo VHDX (disco rígido virtual) da imagem ISO do Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="35cba-226">This step prepares a virtual hard disk (VHDX) file from the Windows Server 2012 ISO image.</span></span> <span data-ttu-id="35cba-227">O VHDX será usado para criar máquinas virtuais durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="35cba-227">The VHDX will be used to create virtual machines during deployment.</span></span> <span data-ttu-id="35cba-228">Uma máquina virtual temporária (VM base) será criada e o Windows Server 2012 será instalado a partir do arquivo ISO.</span><span class="sxs-lookup"><span data-stu-id="35cba-228">A temporary virtual machine (base VM) will be created and Windows Server 2012 will be installed from the ISO file.</span></span> <span data-ttu-id="35cba-229">Depois que a VM for criada, alguns componentes necessários serão instalados e a atualização mais recente do Windows será aplicada.</span><span class="sxs-lookup"><span data-stu-id="35cba-229">After the VM is created, some necessary components will be installed and the latest Windows update will be applied.</span></span> <span data-ttu-id="35cba-230">No final, a VM base será generalizada (sysprep) e limpa, deixando apenas o arquivo de disco virtual gerado.</span><span class="sxs-lookup"><span data-stu-id="35cba-230">At the end, the base VM will be generalized (sysprep) and cleaned up, leaving only the generated virtual disk file.</span></span>

> [!NOTE]
> <span data-ttu-id="35cba-231">Você precisa executar esta etapa apenas para o primeiro dispositivo.</span><span class="sxs-lookup"><span data-stu-id="35cba-231">You need to perform this step for the first appliance only.</span></span> 

<span data-ttu-id="35cba-232">Antes de prosseguir com esta etapa, certifique-se de que a opção corpnet foi criada.</span><span class="sxs-lookup"><span data-stu-id="35cba-232">Before proceeding with this step, make sure that the corpnet switch is created.</span></span> <span data-ttu-id="35cba-233">Além disso, confirme se as seguintes configurações estão corretamente configuradas no CloudConnector.ini arquivo:</span><span class="sxs-lookup"><span data-stu-id="35cba-233">Also, confirm that the following settings are correctly configured in the CloudConnector.ini file:</span></span>

- <span data-ttu-id="35cba-234">[Rede] CorpnetSwitchName</span><span class="sxs-lookup"><span data-stu-id="35cba-234">[Network]CorpnetSwitchName</span></span>

- <span data-ttu-id="35cba-235">[Comum] BaseVMIP</span><span class="sxs-lookup"><span data-stu-id="35cba-235">[Common]BaseVMIP</span></span>

- <span data-ttu-id="35cba-236">[Rede] CorpnetIPPrefixLength</span><span class="sxs-lookup"><span data-stu-id="35cba-236">[Network]CorpnetIPPrefixLength</span></span>

- <span data-ttu-id="35cba-237">[Rede] CorpnetDefaultGateway</span><span class="sxs-lookup"><span data-stu-id="35cba-237">[Network]CorpnetDefaultGateway</span></span>

- <span data-ttu-id="35cba-238">[Rede] CorpnetDNSIPAddress</span><span class="sxs-lookup"><span data-stu-id="35cba-238">[Network]CorpnetDNSIPAddress</span></span>

<span data-ttu-id="35cba-239">Inicie um console do PowerShell como administrador e execute o seguinte cmdlet para converter a imagem ISO em um disco rígido virtual (VHD):</span><span class="sxs-lookup"><span data-stu-id="35cba-239">Start a PowerShell console as administrator and run the following cmdlet to convert the ISO image to a virtual hard disk (VHD):</span></span>

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

<span data-ttu-id="35cba-240">Especifique o caminho completo, incluindo o nome do arquivo, para a imagem ISO.</span><span class="sxs-lookup"><span data-stu-id="35cba-240">Specify the full path, including file name, to the ISO image.</span></span> <span data-ttu-id="35cba-241">Por exemplo: C:\ISO\WindowsServer2012R2.iso.</span><span class="sxs-lookup"><span data-stu-id="35cba-241">For example: C:\ISO\WindowsServer2012R2.iso.</span></span>

<span data-ttu-id="35cba-242">O arquivo VHD criado é armazenado na pasta Diretório **de Sites** \Bits\VHD.</span><span class="sxs-lookup"><span data-stu-id="35cba-242">The created VHD file is stored in the **Site Directory** \Bits\VHD folder.</span></span> <span data-ttu-id="35cba-243">Você pode obter o caminho para o **Diretório de Sites** executando o **Get-CcSiteDirectory**.</span><span class="sxs-lookup"><span data-stu-id="35cba-243">You can get the path to the **Site Directory** by running the **Get-CcSiteDirectory**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="35cba-244">Por padrão, as configurações de proxy não são configuradas na VM base.</span><span class="sxs-lookup"><span data-stu-id="35cba-244">By default, proxy settings are not configured on the base VM.</span></span> <span data-ttu-id="35cba-245">Se um proxy for necessário em seu ambiente de rede para atualizar a VM por meio do Windows Update, você deverá adicionar a opção -PauseBeforeUpdate ao executar "Convert-CcIsoToVhdx".</span><span class="sxs-lookup"><span data-stu-id="35cba-245">If a proxy is required in your network environment to update the VM via Windows Update, you should add the -PauseBeforeUpdate switch when you run "Convert-CcIsoToVhdx".</span></span> <span data-ttu-id="35cba-246">O script será pausado antes do Windows Update e você terá a chance de configurar manualmente o proxy na VM.</span><span class="sxs-lookup"><span data-stu-id="35cba-246">The script will pause before Windows Update and you'll have a chance to manually set up proxy on the VM.</span></span> <span data-ttu-id="35cba-247">Depois que o proxy for configurado e a VM puder acessar a Internet, você poderá retomar o script para concluir as etapas restantes.</span><span class="sxs-lookup"><span data-stu-id="35cba-247">After the proxy is setup and the VM can access Internet, you can resume the script to complete the remaining steps.</span></span> 

### <a name="create-vhds-for-a-multi-site-deployment"></a><span data-ttu-id="35cba-248">Criar VHDs para uma implantação de vários sites</span><span class="sxs-lookup"><span data-stu-id="35cba-248">Create VHDs for a multi-site deployment</span></span>

<span data-ttu-id="35cba-249">Esta é uma etapa opcional que se aplica somente a implantações de vários sites.</span><span class="sxs-lookup"><span data-stu-id="35cba-249">This is an optional step that applies only to multi-site deployments.</span></span>

<span data-ttu-id="35cba-250">Se você estiver implantando uma implantação de vários sites, não será necessário converter o ISO em um VHD para cada site.</span><span class="sxs-lookup"><span data-stu-id="35cba-250">If you are deploying a multi-site deployment, you do not need to convert the ISO to a VHD for each site.</span></span> <span data-ttu-id="35cba-251">Você pode copiar o VHDX criado para o primeiro site para o servidor host de um segundo site.</span><span class="sxs-lookup"><span data-stu-id="35cba-251">You can copy the VHDX created for the first site to the host server for a second site.</span></span>

 <span data-ttu-id="35cba-252">Copie o arquivo para o mesmo local de arquivo (pasta Diretório de **Sites** \Bits\VHD) e com o mesmo nome de arquivo, no servidor host de um site adicional.</span><span class="sxs-lookup"><span data-stu-id="35cba-252">Copy the file to the same file location ( **Site Directory** \Bits\VHD folder), and with the same file name, on the host server for an additional site.</span></span>

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a><span data-ttu-id="35cba-253">Definir a política de Execução do PowerShell como RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="35cba-253">Set the PowerShell Execution policy to RemoteSigned</span></span>

<span data-ttu-id="35cba-254">Os scripts do PowerShell fornecidos exigem que a política de execução seja definida como RemoteSigned.</span><span class="sxs-lookup"><span data-stu-id="35cba-254">The PowerShell scripts provided require that the execution policy be set to RemoteSigned.</span></span> <span data-ttu-id="35cba-255">Para ver a configuração atual, abra um console do PowerShell como administrador e execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="35cba-255">To see the current setting, open a PowerShell console as administrator and then run the following cmdlet:</span></span>

```powershell
Get-ExecutionPolicy
```

<span data-ttu-id="35cba-256">Se não estiver definido como "RemoteSigned", execute o seguinte cmdlet para alterá-lo:</span><span class="sxs-lookup"><span data-stu-id="35cba-256">If it is not set to "RemoteSigned," run the following cmdlet to change it:</span></span>

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a><span data-ttu-id="35cba-257">Alterar a Política de Grupo local no computador host (versões 1.4.1 e anteriores)</span><span class="sxs-lookup"><span data-stu-id="35cba-257">Change local Group Policy on the host machine (versions 1.4.1 and earlier)</span></span>

> [!NOTE]
> <span data-ttu-id="35cba-258">Essa tarefa não é necessária para as versões 1.4.2 e posteriores do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="35cba-258">This task is not required for Cloud Connector versions 1.4.2 and later.</span></span> 

<span data-ttu-id="35cba-259">A conta CceService é criada durante a implantação do Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="35cba-259">The CceService account is created during the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="35cba-260">Ele executa o Serviço de Gerenciamento do Cloud Connector e exige permissão para desinstalar o cloudconnector.msi.</span><span class="sxs-lookup"><span data-stu-id="35cba-260">It runs the Cloud Connector Management Service and requires permission to uninstall the cloudconnector.msi.</span></span> <span data-ttu-id="35cba-261">Você deve alterar a configuração da política de grupo no computador host do Cloud Connector para especificar que o Registro do usuário não deve ser descarregado quando o usuário faz o login.</span><span class="sxs-lookup"><span data-stu-id="35cba-261">You must change the group policy setting on the Cloud Connector host machine to specify that the user registry should not be unloaded when the user logs off.</span></span> <span data-ttu-id="35cba-262">Siga as etapas abaixo:</span><span class="sxs-lookup"><span data-stu-id="35cba-262">Follow the steps below:</span></span>

### <a name="to-change-the-group-policy-setting"></a><span data-ttu-id="35cba-263">Para alterar a configuração da Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="35cba-263">To change the Group Policy setting</span></span>

1. <span data-ttu-id="35cba-264">Abra o **Editor de Política de** Grupo executando gpedit.msc.</span><span class="sxs-lookup"><span data-stu-id="35cba-264">Open the **Group Policy Editor** by running gpedit.msc.</span></span>

2. <span data-ttu-id="35cba-265">No **Editor** de Política de Grupo, navegue até Modelos Administrativos > System > UserProfile > Não descarregar o registro do usuário com força no logoff do usuário.</span><span class="sxs-lookup"><span data-stu-id="35cba-265">In the **Group Policy Editor**, navigate to Administrative Templates > System > UserProfile > Do not forcefully unload the user registry at user logoff.</span></span> 

3. <span data-ttu-id="35cba-266">Definir seu valor como **Enabled**.</span><span class="sxs-lookup"><span data-stu-id="35cba-266">Set its value to **Enabled**.</span></span>

## <a name="set-up-your-microsoft-365-or-office-365-organization"></a><span data-ttu-id="35cba-267">Configurar sua organização do Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="35cba-267">Set up your Microsoft 365 or Office 365 organization</span></span>

<span data-ttu-id="35cba-268">Uma organização do Microsoft 365 ou Office 365 com o Skype for Business Online e o Sistema de Telefonia é necessária.</span><span class="sxs-lookup"><span data-stu-id="35cba-268">A Microsoft 365 or Office 365 organization with Skype for Business Online and Phone System is required.</span></span> <span data-ttu-id="35cba-269">Certifique-se de que seu locatário está configurado e configurado antes de tentar usar o Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="35cba-269">Make sure your tenant is set up and configured before attempting to use Cloud Connector.</span></span>

<span data-ttu-id="35cba-270">Algumas etapas de configuração do Microsoft 365 e office 365 exigem que você use o TRPS (Tenant Remote PowerShell) para configurar sua organização do Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="35cba-270">Some Microsoft 365 and Office 365 setup steps require you to use Tenant Remote PowerShell (TRPS) to configure your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="35cba-271">**Isso deve ser instalado no servidor host.**</span><span class="sxs-lookup"><span data-stu-id="35cba-271">**This should be installed on the host server.**</span></span> <span data-ttu-id="35cba-272">Você pode baixar o módulo do Skype for Business Online para PowerShell em: [Skype for Business Online, Módulo do Windows PowerShell.](https://www.microsoft.com/download/details.aspx?id=39366)</span><span class="sxs-lookup"><span data-stu-id="35cba-272">You can download the Skype for Business Online module for PowerShell from: [Skype for Business Online, Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="35cba-273">Crie uma conta dedicada de administrador do Skype for Business para o gerenciamento online do Cloud Connector, por exemplo, CceOnlineManagmentAdministrator.</span><span class="sxs-lookup"><span data-stu-id="35cba-273">Create a dedicated Skype for Business administrator account for Cloud Connector online management, for example CceOnlineManagmentAdministrator.</span></span> <span data-ttu-id="35cba-274">Essa conta será usada pelo dispositivo para adicionar ou remover dispositivo, habilitar ou desabilitar a atualização automática do sistema operacional, habilitar ou desabilitar a atualização binária automática.</span><span class="sxs-lookup"><span data-stu-id="35cba-274">This account will be used by appliance to add or remove appliance, enable or disable automatic OS update, enable or disable automatic binary update.</span></span> <span data-ttu-id="35cba-275">De configurar a senha dessa conta para nunca expirar, para que você não precise alterá-la para o serviço sempre que ela expirar.</span><span class="sxs-lookup"><span data-stu-id="35cba-275">Set the password for this account to never expire so that you do not need to change it for the service each time it expires.</span></span>


