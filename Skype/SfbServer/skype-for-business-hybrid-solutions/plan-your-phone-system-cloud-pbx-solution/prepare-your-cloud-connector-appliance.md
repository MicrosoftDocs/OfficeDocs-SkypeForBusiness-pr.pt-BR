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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: Saiba como preparar seu aparelho do Cloud Connector para implantação e uso com o sistema telefônico no Office 365 (Cloud PBX).
ms.openlocfilehash: f2140eb0be25ba0b6935f389e5ae7b27bfc37359
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286996"
---
# <a name="prepare-your-cloud-connector-appliance"></a><span data-ttu-id="7cf1f-103">Preparar o dispositivo do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="7cf1f-103">Prepare your Cloud Connector appliance</span></span>

<span data-ttu-id="7cf1f-104">Saiba como preparar seu aparelho do Cloud Connector para implantação e uso com o sistema telefônico no Office 365 (Cloud PBX).</span><span class="sxs-lookup"><span data-stu-id="7cf1f-104">Learn about how to prepare your Cloud Connector appliance for deployment and use with Phone System in Office 365 (Cloud PBX).</span></span>

<span data-ttu-id="7cf1f-105">Esta seção descreve como obter os arquivos de instalação do Skype for Business Cloud Connector Edition, instalar o software do Cloud Connector e preparar o dispositivo do Cloud Connector para implantação.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-105">This section describes how to get the Skype for Business Cloud Connector Edition installation files, install Cloud Connector software, and prepare your Cloud Connector appliance for deployment.</span></span> <span data-ttu-id="7cf1f-106">Depois de ter concluído todas as etapas desta seção, você estará pronto para implantar o Cloud Connector em um único site ou em vários sites.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-106">After you have completed all steps in this section, you will be ready to deploy Cloud Connector for a single site or multiple sites.</span></span> <span data-ttu-id="7cf1f-107">Se você tiver uma implantação existente do conector de nuvem e ainda não tiver atualizado para o Cloud Connector versão 2,1, confira [atualizar para uma nova versão do Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="7cf1f-107">If you have an existing Cloud Connector deployment, and you have not yet upgraded to Cloud Connector version 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7cf1f-108">A Microsoft oferece suporte à versão atual do Cloud Connector Edition, versão 2,1.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-108">Microsoft supports the current version of Cloud Connector Edition, version 2.1.</span></span> <span data-ttu-id="7cf1f-109">Se você tiver configurado a atualização automática, o Cloud Connector será atualizado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-109">If you configured automatic update, Cloud Connector will update automatically.</span></span> <span data-ttu-id="7cf1f-110">Se você configurou a atualização manual, será preciso atualizar para a versão 2,1 dentro de 60 dias após a sua versão.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-110">If you configured manual update, you will need to upgrade to version 2.1 within 60 days of its release.</span></span> <span data-ttu-id="7cf1f-111">A Microsoft dará suporte à versão anterior por 60 dias após o lançamento do 2,1 para permitir que você atualize o tempo.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-111">Microsoft will support the previous version for 60 days after the release of 2.1 to allow you time to upgrade.</span></span> 

> [!NOTE]
> <span data-ttu-id="7cf1f-112">Para o Cloud Connector versão 2,1 e posterior, o host Appliance deve ter o .NET Framework 4.6.1 ou posterior instalado.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-112">For Cloud Connector version 2.1 and later, the host appliance must have .NET Framework 4.6.1 or later installed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="7cf1f-113">Para uma implantação bem-sucedida, ao executar os cmdlets para configurar o Skype for Business Cloud Connector Edition, use sempre a mesma sessão de console que você iniciou.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-113">For successful deployment, when you run the cmdlets to configure Skype for Business Cloud Connector Edition, always use the same console session as the one you started in.</span></span> <span data-ttu-id="7cf1f-114">Evite alternar entre diferentes sessões durante a implantação e a configuração.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-114">Avoid switching to different sessions during the deployment and configuration.</span></span> 

> [!NOTE]
> <span data-ttu-id="7cf1f-115">Existem algumas etapas que você executa somente para o primeiro dispositivo de sua implantação: criar um compartilhamento para o diretório do site, baixar os bits e preparar um arquivo VHDX (disco rígido virtual) com a imagem ISO do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-115">There are some steps that you perform only for the first appliance in your deployment: creating a share for the site directory, downloading the bits, and preparing a virtual hard disk (VHDX) file from the Windows Server ISO image.</span></span> 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a><span data-ttu-id="7cf1f-116">Baixar o instalador do Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="7cf1f-116">Download the Skype for Business Cloud Connector Edition installer</span></span>

1. <span data-ttu-id="7cf1f-117">No servidor host onde as VMs do conector de nuvem serão executadas, baixe os arquivos de [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)instalação:.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-117">On the host server where the Cloud Connector VMs will run, download the installation files: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="7cf1f-118">O servidor host precisa acessar a Internet durante a instalação do Cloud Connector porque arquivos adicionais são baixados durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-118">The host server must be able to access the Internet during the installation of Cloud Connector because additional files are downloaded during the installation.</span></span> 

2. <span data-ttu-id="7cf1f-119">Execute o instalador e aceite os valores padrão durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-119">Run the installer and accept the default values during the installation.</span></span>

3. <span data-ttu-id="7cf1f-120">Confirme se a instalação foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-120">Confirm that the installation completed successfully.</span></span>

## <a name="verify-the-installation-and-configure-the-environment"></a><span data-ttu-id="7cf1f-121">Verificar a instalação e configurar o ambiente</span><span class="sxs-lookup"><span data-stu-id="7cf1f-121">Verify the installation and configure the environment</span></span>

1. <span data-ttu-id="7cf1f-122">Abra um console do PowerShell como administrador e confirme se os cmdlets do Skype for Business Cloud Connector Edition estão disponíveis usando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7cf1f-122">Open a PowerShell console as administrator and confirm that the Skype for Business Cloud Connector Edition cmdlets are available using the following cmdlet:</span></span>

   ```
   Get-Command *-Cc*
   ```

    <span data-ttu-id="7cf1f-123">O comando deve retornar uma lista de cmdlets para o Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-123">The command should return a list of cmdlets for Skype for Business Cloud Connector Edition.</span></span>

2. <span data-ttu-id="7cf1f-124">Os arquivos VHDs, SfBBits e VersionInfo serão armazenados no **Diretório de Sites**.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-124">The VHDs, SfBBits, and VersionInfo files will be stored in the **Site Directory**.</span></span>

    <span data-ttu-id="7cf1f-125">Você pode localizar o **Diretório de Sites** com o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7cf1f-125">You can find the location of the **Site Directory** with the following cmdlet:</span></span>

   ```
   Get-CcSiteDirectory
   ```

    <span data-ttu-id="7cf1f-126">O comando deve retornar um local no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-126">The command should return a location in your file system.</span></span> <span data-ttu-id="7cf1f-127">O local pode ser uma pasta local ou um compartilhamento de aquivo.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-127">The location can be a local folder or a file share.</span></span> <span data-ttu-id="7cf1f-128">O local padrão para o **Diretório de Sites** é: %USERPROFILE%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-128">The default location for the **Site Directory** is: %USERPROFILE%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="7cf1f-129">O local padrão deve ser alterado para um compartilhamento de aquivo no primeiro dispositivo criado em cada site.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-129">The default location should be changed to a file share on the first appliance created in each site.</span></span>

    <span data-ttu-id="7cf1f-130">O local selecionado deve ser:</span><span class="sxs-lookup"><span data-stu-id="7cf1f-130">The location you select must be:</span></span>

   - <span data-ttu-id="7cf1f-131">Criado no primeiro dispositivo criado em cada site.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-131">Created on the first appliance created in each site.</span></span>

   - <span data-ttu-id="7cf1f-132">Uma pasta compartilhada acessível por outros servidores host (dispositivos) no mesmo site.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-132">A shared folder that is accessible by the other host servers (appliances) in the same site.</span></span>

     <span data-ttu-id="7cf1f-133">Para definir o **Diretório de Sites** para um local diferente do padrão, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7cf1f-133">To set the **Site Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```
   Set-CcSiteDirectory <UNC File path>
   ```

    <span data-ttu-id="7cf1f-134">Se você estiver implantando alta disponibilidade para o site, execute o cmdlet para definir o \*\*Diretório de Sites \*\* para o mesmo local em cada servidor host do site.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-134">If you are deploying High Availability (HA) for the site, make sure you run the cmdlet to set the **Site Directory** to the same location on each host server within the site.</span></span>

    <span data-ttu-id="7cf1f-135">Ao fazer logon e implantar cada aplicativo no site, verifique se a conta de logon atual tem o acesso certo ao diretório de **sites**.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-135">When you log on and deploy each appliance in the site, make sure your current logon account has the right access to the **Site Directory**.</span></span>

3. <span data-ttu-id="7cf1f-136">O **diretório de aplicativos** é o diretório raiz de trabalho local para o Skype for Business Cloud Connector Edition e o local onde certificados, instâncias e registros externos são salvos.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-136">The **Appliance Directory** is the local working root directory for Skype for Business Cloud Connector Edition, and the location where external certificates, instances, and logs are saved.</span></span> <span data-ttu-id="7cf1f-137">O local padrão é: %USERPROFILE%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-137">The default location is: %USERPROFILE%\CloudConnector\ApplianceRoot.</span></span>

    <span data-ttu-id="7cf1f-138">Você pode localizar o **Diretório de Sites** executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7cf1f-138">To find the location of the **Appliance Directory**, run the following cmdlet:</span></span>

   ```
   Get-CcApplianceDirectory
   ```

    <span data-ttu-id="7cf1f-139">Para definir o **Diretório de Dispositivos** para um local diferente do padrão, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7cf1f-139">To set the **Appliance Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```
   Set-CcApplianceDirectory <File path>
   ```

    <span data-ttu-id="7cf1f-140">O Diretório de Dispositivos deve ser definido em uma pasta local no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-140">The Appliance Directory should be set to a local folder on the appliance.</span></span> <span data-ttu-id="7cf1f-141">Você só deve definir o **diretório do aparelho** antes de iniciar a implantação do Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-141">You should only set the **Appliance Directory** before you start the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="7cf1f-142">Se você alterá-lo após a implantação, será necessário reimplantar o servidor host.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-142">If you change it after deployment, you'll need to redeploy the host server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="7cf1f-143">O caminho do **Diretório de Dispositivos** não deve conter espaços.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-143">The path to the **Appliance Directory** must not contain any spaces.</span></span>

## <a name="set-the-path-for-the-external-edge-certificate"></a><span data-ttu-id="7cf1f-144">Definir o caminho do certificado externo de Borda</span><span class="sxs-lookup"><span data-stu-id="7cf1f-144">Set the path for the external Edge certificate</span></span>

- <span data-ttu-id="7cf1f-p107">Execute o cmdlet a seguir para definir o caminho do certificado externo de Borda, incluindo o nome do arquivo. Por exemplo: C:\certs\cce\ap.contoso.com.pfx. O certificado deve conter chaves privadas.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-p107">Run the following cmdlet to set the path, including the file name, to the external Edge certificate. For example: C:\certs\cce\ap.contoso.com.pfx. The certificate must contain private keys.</span></span>

  ```
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > <span data-ttu-id="7cf1f-148">Note que o parâmetro -Target é específico à versão 1.4.2 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-148">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

    <span data-ttu-id="7cf1f-149">Especificar o caminho completo do certificado externo, incluindo o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-149">Specify the full path to the external certificate, including the file name.</span></span> <span data-ttu-id="7cf1f-150">O certificado pode ser armazenado localmente ou em um compartilhamento de arquivo.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-150">The certificate can be stored locally or on a file share.</span></span> <span data-ttu-id="7cf1f-151">Se o certificado for armazenado em uma pasta compartilhada, essa pasta deverá ser criada no primeiro dispositivo de cada site e deverá ser acessível por outros dispositivos pertencentes ao mesmo site.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-151">If the certificate is stored in a shared folder, the shared folder must be created on the first appliance of each site and must be accessible by other appliances belonging to the same site.</span></span> <span data-ttu-id="7cf1f-152">Esse cmdlet copia o certificado externo para o **Diretório de Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-152">This cmdlet copies the external certificate to the **Appliance Directory**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="7cf1f-153">**Se você tiver atualizado para o Cloud Connector versão 1.4.2 ou posteriores**, verifique se o certificado externo preparado contém chaves privadas e a cadeia completa de certificados, inclusive o certificado de Autoridade de Certificação raiz e os certificados de Autoridade de Certificação intermediária.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-153">**If you have updated to Cloud Connector version 1.4.2 or later**, make sure your prepared external certificate contains private keys and the full certificate chain including the root CA certificate and the intermediate CA certificates.</span></span> <span data-ttu-id="7cf1f-154">**Se você NÃO tiver atualizado ainda para o Cloud Connector versão 1.4.2**, certifique-se de que  o certificado externo preparado contém chaves privadas.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-154">**If you have NOT yet updated to Cloud Connector version 1.4.2**, make sure your prepared external certificate contains private keys.</span></span> <span data-ttu-id="7cf1f-155">Esse certificado externo deve ser emitido pela Autoridade de Certificação que é confiável para o Windows por padrão.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-155">This external certificate must be issued by a Certificate Authority that is trusted by Windows by default.</span></span>

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a><span data-ttu-id="7cf1f-156">Definir o caminho do certificado de gateway PSTN externo/SBC</span><span class="sxs-lookup"><span data-stu-id="7cf1f-156">Set the path for the external PSTN gateway/SBC certificate</span></span>

<span data-ttu-id="7cf1f-157">Se você estiver usando o TLS entre o Servidor de Mediação e o gateway PSTN/SBC, execute o seguinte cmdlet para definir o caminho, incluindo o nome do arquivo, para o certificado de gateway.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-157">If you are using TLS between the Mediation Server and the PSTN gateway/SBC, run the following cmdlet to set the path, including the file name, to the gateway certificate.</span></span> <span data-ttu-id="7cf1f-158">Por exemplo: C:\certs\cce\sbc.contoso.com.cer.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-158">For example: C:\certs\cce\sbc.contoso.com.cer.</span></span> <span data-ttu-id="7cf1f-159">O certificado deve conter a Autoridade de Certificação raiz e a cadeia intermediária para o certificado atribuído ao gateway:</span><span class="sxs-lookup"><span data-stu-id="7cf1f-159">The certificate must contain the root CA and the intermediate chain for the certificate assigned to the gateway:</span></span>

```
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> <span data-ttu-id="7cf1f-160">Note que o parâmetro -Target é específico à versão 1.4.2 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-160">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

## <a name="create-virtual-switches-in-hyper-v-manager"></a><span data-ttu-id="7cf1f-161">Criar comutadores virtuais no Gerenciador do Hyper-V</span><span class="sxs-lookup"><span data-stu-id="7cf1f-161">Create virtual switches in Hyper-V Manager</span></span>

1. <span data-ttu-id="7cf1f-162">Abra o**Gerenciador de comutador virtual**do **Hyper-V Manager** > e selecione **novo Gerenciador de comutador virtual**.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-162">Open **Hyper-V Manager** > **Virtual Switch Manager**, and select **New Virtual Switch Manager**.</span></span>

2. <span data-ttu-id="7cf1f-163">Crie um comutador virtual externo e associe-o ao adaptador de rede física que está conectado ao domínio da rede interna:</span><span class="sxs-lookup"><span data-stu-id="7cf1f-163">Create an External virtual switch and bind it to the physical network adapter that is connected to your internal network domain:</span></span>

    <span data-ttu-id="7cf1f-164">Selecione a opção **Permitir que o sistema operacional de gerenciamento compartilhe este adaptador de rede** para esse comutador virtual.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-164">Select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

3. <span data-ttu-id="7cf1f-165">Crie um comutador virtual externo e vincule-o ao adaptador de rede física que está roteado para a Internet:</span><span class="sxs-lookup"><span data-stu-id="7cf1f-165">Create an External virtual switch and bind it to the physical network adapter that is routed to the Internet:</span></span>

    <span data-ttu-id="7cf1f-166">Desmarque **permitir que o sistema operacional de gerenciamento Compartilhe este adaptador de rede** para este comutador virtual.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-166">De-select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

4. <span data-ttu-id="7cf1f-167">Defina o nome da opção que conecta a sua rede de perímetro ao seu domínio da rede interna **SfB do CCE corpnet**.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-167">Set the name of the switch that connects your perimeter network to your internal network domain **SfB CCE Corpnet Switch**.</span></span>

    <span data-ttu-id="7cf1f-168">Defina o nome da opção que conecta a sua rede de perímetro à Internet **SFB CCE Internet**.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-168">Set the name of the switch that connects your perimeter network to the Internet **SfB CCE Internet Switch**.</span></span>

## <a name="update-the-cloudconnectorini-configuration-file"></a><span data-ttu-id="7cf1f-169">Atualizar o arquivo de configuração CloudConnector.ini</span><span class="sxs-lookup"><span data-stu-id="7cf1f-169">Update the CloudConnector.ini configuration file</span></span>

<span data-ttu-id="7cf1f-170">Prepare o arquivo CloudConnector. ini usando as informações coletadas em [determinar parâmetros de implantação](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) no tópico [plano para o Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) .</span><span class="sxs-lookup"><span data-stu-id="7cf1f-170">Prepare the CloudConnector.ini file using the information you gathered in [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) in the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span>

<span data-ttu-id="7cf1f-171">Para atualizar o arquivo, execute o seguinte cmdlet para obter o modelo (CloudConnector.Sample.ini):</span><span class="sxs-lookup"><span data-stu-id="7cf1f-171">To update the file, first run the following cmdlet to get the sample template (CloudConnector.Sample.ini):</span></span>

```
Export-CcConfigurationSampleFile
```

<span data-ttu-id="7cf1f-172">O modelo é armazenado no **Diretório de Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-172">The sample template is stored in the **Appliance Directory**.</span></span>

<span data-ttu-id="7cf1f-173">Depois de atualizá-lo com os valores para seu ambiente, salve o arquivo como CloudConnector.ini no **Diretório de Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-173">After you update it with the values for your environment, save the file as CloudConnector.ini in the **Appliance Directory**.</span></span> <span data-ttu-id="7cf1f-174">Você pode executar o **Get-CcApplianceDirectory** para determinar o caminho do **Diretório de Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-174">You can run **Get-CcApplianceDirectory** to determine the path to the **Appliance Directory**.</span></span>

<span data-ttu-id="7cf1f-175">Ao atualizar o arquivo .ini, considere o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7cf1f-175">When updating the .ini file, consider the following:</span></span>

> [!NOTE]
> <span data-ttu-id="7cf1f-176">Nem todos os valores para o arquivo .ini são mencionados nesta seção, somente aqueles com uma consideração especial são incluídos aqui.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-176">Not all values for the .ini file are discussed in this section, only those with a special consideration are covered here.</span></span> <span data-ttu-id="7cf1f-177">Para obter uma lista completa, consulte a seção [determinar parâmetros de implantação](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) do tópico [planejar para o Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) .</span><span class="sxs-lookup"><span data-stu-id="7cf1f-177">For a full list, see the [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) section of the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span> <span data-ttu-id="7cf1f-178">Para obter mais informações sobre quais valores devem ser alterados para dispositivo adicionais ou novos sites, consulte [Único site com alta disponibilidade em comparação com implantações de vários sites](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) no tópico [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="7cf1f-178">For more information about what values need to be changed for additional appliances or new sites, see [Single site with High Availability (HA) compared to multi-site deployments](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) in the topic [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 

- <span data-ttu-id="7cf1f-p113">**SiteName:** o valor padrão é **Site1**. Você deve atualizá-lo antes de implantar o Cloud Connector, pois quando você executar **Register-CcAppliance** para registrar um dispositivo em um site novo ou existente, o cmdlet usará **SiteName** para determinar qual site registrar.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-p113">**SiteName:** The default value is **Site1**. You must update it before you deploy Cloud Connector, because when you run **Register-CcAppliance** to register an appliance to an existing or new site, the cmdlet will use **SiteName** to determine which site to register.</span></span>

     <span data-ttu-id="7cf1f-181">Se você deseja registrar o dispositivo em um site novo, o valor de **SiteName** deverá ser exclusivo e diferente dos sites existentes.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-181">If you want to register the appliance to a new site, the value of **SiteName** must be unique and different from existing sites.</span></span> <span data-ttu-id="7cf1f-182">Se você quiser registrar o aplicativo em um site existente, o valor de **SiteName** no arquivo. ini deve corresponder ao nome definido na configuração do locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-182">If you want to register the appliance to an existing site, the value for **SiteName** in .ini file must match the name defined in your Office 365 tenant configuration.</span></span> <span data-ttu-id="7cf1f-183">Se você estiver copiando um arquivo de configuração de um site para outro, atualize o valor de **SiteName** devidamente para cada site.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-183">If you are copying a configuration file from one site to another, make sure you update the value for **SiteName** for each site accordingly.</span></span>

- <span data-ttu-id="7cf1f-184">**ServerName:** O nome do servidor não deve conter o nome do domínio e deve ser limitado a 15 caracteres. </span><span class="sxs-lookup"><span data-stu-id="7cf1f-184">**ServerName:** The server name should not contain the domain name and should be limited to 15 characters.</span></span>

- <span data-ttu-id="7cf1f-185">**HardwareType:** Se você não definir ou deixar o valor como NULL, o valor padrão de **normal** será usado.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-185">**HardwareType:** If you don't set or leave the value to null, the default value of **Normal** will be used.</span></span> <span data-ttu-id="7cf1f-186">Use **normal** se você planeja implantar a versão maior do conector de nuvem para dar suporte a chamadas simultâneas de 500 por máquina host, conforme descrito em [plano para o Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="7cf1f-186">Use **Normal** if you plan to deploy the larger version of Cloud Connector to support 500 simultaneous calls per host machine as described in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> <span data-ttu-id="7cf1f-187">Use **Mínimo** para uma implantação menor que permita 50 chamadas simultâneas.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-187">Use **Minimum** for a smaller deployment that supports 50 simultaneous calls.</span></span>

- <span data-ttu-id="7cf1f-188">**Comutadores virtuais de Internet/Corpnet/Gerenciamento**: adicione o nome dos comutadores criados.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-188">**Internet/Corpnet/Management virtual switches:**: Add the name of the virtual switches you have created.</span></span> <span data-ttu-id="7cf1f-189">Para o comutador virtual de gerenciamento, apenas deixe o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-189">For the management virtual switch, leave the default value.</span></span> <span data-ttu-id="7cf1f-190">O script de implantação o criará no início da implantação e o excluirá quando a implantação terminar.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-190">The deployment script will create the management virtual switch at the beginning of deployment and delete it when the deployment finishes.</span></span>

- <span data-ttu-id="7cf1f-p117">**ManagementIPPrefix:** o ManagementIPPrefix, na seção Rede, deve ser uma sub-rede diferente dos outros IPs internos. Por exemplo, como o valor padrão mostra, ManagementIPPrefix é 192.168.213.0, enquanto o IPAddress do AD é 192.168.0.238.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-p117">**ManagementIPPrefix:** ManagementIPPrefix in the Network section must be a different subnet from other internal IPs. For example, as the default value shows, ManagementIPPrefix is 192.168.213.0, while AD IPAddress is 192.168.0.238.</span></span>

    <span data-ttu-id="7cf1f-p118">Os scripts de implantação criam um adaptador de rede de gerenciamento em cada máquina virtual, atribui a cada uma delas um IP de gerenciamento e as conecta a um comutador virtual de gerenciamento. Isso permite que o servidor host se conecte a todas as máquinas virtuais e as gerencie por meio da rede de gerenciamento. O comutador virtual de gerenciamento é excluído quando a implantação é concluída.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-p118">The deployment scripts create a management network adapter on each virtual machine, assign a management IP, and connect it to a management virtual switch. This enables the host server to connect to and manage each virtual machine via this management network. The management virtual switch is deleted when the deployment is finished.</span></span>

- <span data-ttu-id="7cf1f-196">**Configurações específicas da VM base:** as configurações apresentadas nesta seção devem ser configuradas para o cmdlet **Convert-CcIsoToVhdx**.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-196">**Base VM specific configurations:** Settings in this section must be configured for the **Convert-CcIsoToVhdx** cmdlet.</span></span>

    <span data-ttu-id="7cf1f-p119">Durante a preparação da imagem da VM base, ela será conectada ao comutador de rede interno. As seguintes configurações são essenciais para a VM acessar a Internet:</span><span class="sxs-lookup"><span data-stu-id="7cf1f-p119">During base VM image preparation, the base VM will be connected to the internal network switch. The following settings are critical for the VM to be able to access the Internet:</span></span>

  - <span data-ttu-id="7cf1f-199">[Common]BaseVMIP: o endereço IP corpnet que será atribuído à VM base.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-199">[Common]BaseVMIP: the corpnet IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="7cf1f-200">[Network]CorpnetDefaultGateway: o gateway padrão a ser atribuído à VM base.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-200">[Network]CorpnetDefaultGateway: the default gateway to be assigned to the base VM.</span></span>

  - <span data-ttu-id="7cf1f-201">[Network]CorpnetDNSIPAddress: o endereço IP do DNS que será atribuído à VM base.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-201">[Network]CorpnetDNSIPAddress: the DNS IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="7cf1f-202">[Network]WSUSServer: o endereço IP do Windows Server Update Service.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-202">[Network]WSUSServer: the IP address of Windows Server Update Service.</span></span>

  - <span data-ttu-id="7cf1f-203">[Network]WSUSServer: o endereço IP do servidor de status do Windows Server Update Service.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-203">[Network]WSUSStatusServer: the IP address of Windows Server Update Service status server.</span></span>

  - <span data-ttu-id="7cf1f-204">[Network]EnableReferSupport: isso definirá se o suporte para SIP REFER está habilitado ou desabilitado na Configuração do Tronco em seu IP/PBX.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-204">[Network]EnableReferSupport: this will define whether SIP REFER support is enabled or disabled on the Trunk Configuration to your IP/PBX.</span></span>

- <span data-ttu-id="7cf1f-205">**IPs externos:**</span><span class="sxs-lookup"><span data-stu-id="7cf1f-205">**Internal IPs:**</span></span>

  - <span data-ttu-id="7cf1f-206">Verifique se a máscara de sub-rede CorpnetIPPrefixLength está correta.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-206">Make sure subnet mask CorpnetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="7cf1f-207">Certifique-se de que não haja conflitos de IP para estes IPs internos.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-207">Make sure there are no IP conflicts for these internal IPs.</span></span>

- <span data-ttu-id="7cf1f-208">**IPs externos:**</span><span class="sxs-lookup"><span data-stu-id="7cf1f-208">**External IPs:**</span></span>

  - <span data-ttu-id="7cf1f-209">Para o IP público do Sr: especifique ExternalMRIPs para não NAT ou ExternalMRPublicIPs para NAT.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-209">For MR public IP: specify either ExternalMRIPs for non-NAT or ExternalMRPublicIPs for NAT.</span></span>

  - <span data-ttu-id="7cf1f-210">ExternalSIPIPs e ExternalMRIPs podem ser iguais.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-210">ExternalSIPIPs and ExternalMRIPs can be the same.</span></span>

  - <span data-ttu-id="7cf1f-211">Verifique se a máscara de sub-rede InternetIPPrefixLength está correta.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-211">Make sure subnet mask InternetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="7cf1f-212">Certifique-se de que não haja conflitos de IP para esses IPs externos.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-212">Make sure there are no IP conflicts for these external IPs.</span></span>

- <span data-ttu-id="7cf1f-213">**Gateways:**</span><span class="sxs-lookup"><span data-stu-id="7cf1f-213">**Gateways:**</span></span>

  - <span data-ttu-id="7cf1f-p120">Se você tiver somente um gateway, remova a seção do gateway secundário. Se você tiver mais de dois gateways, crie seções adicionais copiando e colando a existente e atualizando-a depois.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-p120">If you have only one gateway, remove the section for the secondary gateway. If you have more than two gateways, create additional sections by copying and pasting the existing one and then updating it.</span></span>

  - <span data-ttu-id="7cf1f-216">Verifique se o endereço IP e a porta do(s) gateway(s) estão corretos.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-216">Make sure that the IP address and port of the gateway(s) are correct.</span></span>

  - <span data-ttu-id="7cf1f-217">Para dar suporte ao nível de alta disponibilidade do Gateway PSTN, saia do gateway secundário e adicione os gateways adicionais que você usará.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-217">To support PSTN gateway level HA, leave the secondary gateway, and add any additional gateways you will use.</span></span> <span data-ttu-id="7cf1f-218">Você pode copiar e colar uma entrada existente e atualizá-la.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-218">You can copy and paste an existing entry and then update it.</span></span>

- <span data-ttu-id="7cf1f-219">Opcionalmente, você pode atualizar o valor LocalRoute para restringir números de chamada de saída.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-219">Optionally, you can update the LocalRoute value to restrict outbound call numbers.</span></span>

## <a name="download-the-bits-to-the-site-directory"></a><span data-ttu-id="7cf1f-220">Baixar os bits para o Diretório de Sites</span><span class="sxs-lookup"><span data-stu-id="7cf1f-220">Download the bits to the Site Directory</span></span>

<span data-ttu-id="7cf1f-221">Execute o seguinte cmdlet para baixar os bits e os arquivos de informações de versão para o **Diretório de Sites**:</span><span class="sxs-lookup"><span data-stu-id="7cf1f-221">Run the following cmdlet to download the bits and version information files to the **Site Directory**:</span></span>

```
Start-CcDownload
```

> [!NOTE]
> <span data-ttu-id="7cf1f-222">Você deve executar esta etapa somente para o primeiro dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-222">You need to perform this step for the first appliance only.</span></span> 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a><span data-ttu-id="7cf1f-223">Preparar VHDX (disco virtual base) usando o arquivo ISO baixado</span><span class="sxs-lookup"><span data-stu-id="7cf1f-223">Prepare base virtual disk (VHDX) from the downloaded ISO file</span></span>

<span data-ttu-id="7cf1f-224">Esta etapa prepara o VHDX (arquivo do disco virtual) a partir da imagem ISO do Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-224">This step prepares a virtual hard disk (VHDX) file from the Windows Server 2012 ISO image.</span></span> <span data-ttu-id="7cf1f-225">O VHDX será usado para criar máquinas virtuais durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-225">The VHDX will be used to create virtual machines during deployment.</span></span> <span data-ttu-id="7cf1f-226">Uma máquina virtual temporária (VM base) será criada e o Windows Server 2012 será instalado a partir do arquivo ISO.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-226">A temporary virtual machine (base VM) will be created and Windows Server 2012 will be installed from the ISO file.</span></span> <span data-ttu-id="7cf1f-227">Após a VM ser criada, alguns componentes necessários serão instalados e a atualização mais recente do Windows será aplicada.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-227">After the VM is created, some necessary components will be installed and the latest Windows update will be applied.</span></span> <span data-ttu-id="7cf1f-228">Por fim, a VM base será generalizada (sysprep) e limpa, permanecendo apenas o arquivo de disco virtual gerado.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-228">At the end, the base VM will be generalized (sysprep) and cleaned up, leaving only the generated virtual disk file.</span></span>

> [!NOTE]
> <span data-ttu-id="7cf1f-229">Você deve executar esta etapa somente para o primeiro dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-229">You need to perform this step for the first appliance only.</span></span> 

<span data-ttu-id="7cf1f-p123">Antes de continuar com esta etapa, verifique se o comutador corpnet foi criado. Além disso, confirme se as seguintes configurações estão corretas no arquivo CloudConnector.ini:</span><span class="sxs-lookup"><span data-stu-id="7cf1f-p123">Before proceeding with this step, make sure that the corpnet switch is created. Also, confirm that the following settings are correctly configured in the CloudConnector.ini file:</span></span>

- <span data-ttu-id="7cf1f-232">[Network]CorpnetSwitchName</span><span class="sxs-lookup"><span data-stu-id="7cf1f-232">[Network]CorpnetSwitchName</span></span>

- <span data-ttu-id="7cf1f-233">[Common]BaseVMIP</span><span class="sxs-lookup"><span data-stu-id="7cf1f-233">[Common]BaseVMIP</span></span>

- <span data-ttu-id="7cf1f-234">[Network]CorpnetIPPrefixLength</span><span class="sxs-lookup"><span data-stu-id="7cf1f-234">[Network]CorpnetIPPrefixLength</span></span>

- <span data-ttu-id="7cf1f-235">[Network]CorpnetDefaultGateway</span><span class="sxs-lookup"><span data-stu-id="7cf1f-235">[Network]CorpnetDefaultGateway</span></span>

- <span data-ttu-id="7cf1f-236">[Network]CorpnetDNSIPAddress</span><span class="sxs-lookup"><span data-stu-id="7cf1f-236">[Network]CorpnetDNSIPAddress</span></span>

<span data-ttu-id="7cf1f-237">Inicie um console do PowerShell como administrador e execute o seguinte cmdlet para converter a imagem ISO em um VHD:</span><span class="sxs-lookup"><span data-stu-id="7cf1f-237">Start a PowerShell console as administrator and run the following cmdlet to convert the ISO image to a virtual hard disk (VHD):</span></span>

```
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

<span data-ttu-id="7cf1f-p124">Especifique o caminho completo da imagem ISO. Inclua o nome do arquivo. Por exemplo: C:\ISO\WindowsServer2012R2.iso.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-p124">Specify the full path, including file name, to the ISO image. For example: C:\ISO\WindowsServer2012R2.iso.</span></span>

<span data-ttu-id="7cf1f-240">O arquivo VHD criado é armazenado na pasta \Bits\VHD do **diretório de sites** .</span><span class="sxs-lookup"><span data-stu-id="7cf1f-240">The created VHD file is stored in the **Site Directory** \Bits\VHD folder.</span></span> <span data-ttu-id="7cf1f-241">Você pode obter o caminho do **Diretório de Sites** executando **Get-CcSiteDirectory**.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-241">You can get the path to the **Site Directory** by running the **Get-CcSiteDirectory**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7cf1f-242">Por padrão, as configurações de proxy não são definidas na VM base.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-242">By default, proxy settings are not configured on the base VM.</span></span> <span data-ttu-id="7cf1f-243">Se um proxy for necessário em seu ambiente de rede para atualizar a VM via Windows Update, você deve adicionar a opção-PauseBeforeUpdate ao executar "Convert-CcIsoToVhdx".</span><span class="sxs-lookup"><span data-stu-id="7cf1f-243">If a proxy is required in your network environment to update the VM via Windows Update, you should add the -PauseBeforeUpdate switch when you run "Convert-CcIsoToVhdx".</span></span> <span data-ttu-id="7cf1f-244">O script será pausado antes do Windows Update e você terá a chance de configurar manualmente o proxy na VM.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-244">The script will pause before Windows Update and you'll have a chance to manually set up proxy on the VM.</span></span> <span data-ttu-id="7cf1f-245">Quando a configuração do proxy for concluída e a VM conseguir acessar a Internet, você poderá retomar o script para concluir as etapas restantes.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-245">After the proxy is setup and the VM can access Internet, you can resume the script to complete the remaining steps.</span></span> 

### <a name="create-vhds-for-a-multi-site-deployment"></a><span data-ttu-id="7cf1f-246">Criar VHDs para a implantação de vários sites</span><span class="sxs-lookup"><span data-stu-id="7cf1f-246">Create VHDs for a multi-site deployment</span></span>

<span data-ttu-id="7cf1f-247">Esta é uma etapa opcional que se aplica apenas a implantações de vários sites.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-247">This is an optional step that applies only to multi-site deployments.</span></span>

<span data-ttu-id="7cf1f-p127">Se você estiver fazendo uma implantação de vários sites, não será necessário converter ISO em um VHD para cada site. É possível copiar o VHDX criado para o primeiro site para o servidor host de um segundo site.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-p127">If you are deploying a multi-site deployment, you do not need to convert the ISO to a VHD for each site. You can copy the VHDX created for the first site to the host server for a second site.</span></span>

 <span data-ttu-id="7cf1f-250">Copie o arquivo para o mesmo local de arquivo (pasta \Bits\VHD **do diretório de sites** ) e com o mesmo nome de arquivo no servidor host de um site adicional.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-250">Copy the file to the same file location ( **Site Directory** \Bits\VHD folder), and with the same file name, on the host server for an additional site.</span></span>

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a><span data-ttu-id="7cf1f-251">Definir a política de Execução do PowerShell para RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="7cf1f-251">Set the PowerShell Execution policy to RemoteSigned</span></span>

<span data-ttu-id="7cf1f-p128">Os scripts do PowerShell fornecidos exigem que a política de execução seja definida como RemoteSigned. Para ver a configuração atual, abra um console do PowerShell como administrador e execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7cf1f-p128">The PowerShell scripts provided require that the execution policy be set to RemoteSigned. To see the current setting, open a PowerShell console as administrator and then run the following cmdlet:</span></span>

```
Get-ExecutionPolicy
```

<span data-ttu-id="7cf1f-254">Caso ela não esteja definida como "RemoteSigned”, execute o seguinte cmdlet para alterá-la:</span><span class="sxs-lookup"><span data-stu-id="7cf1f-254">If it is not set to "RemoteSigned," run the following cmdlet to change it:</span></span>

```
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a><span data-ttu-id="7cf1f-255">Alterar a Política de Grupo local na máquina host (versões 1.4.1 e anteriores)</span><span class="sxs-lookup"><span data-stu-id="7cf1f-255">Change local Group Policy on the host machine (versions 1.4.1 and earlier)</span></span>

> [!NOTE]
> <span data-ttu-id="7cf1f-256">Esta tarefa não é necessária para o Cloud Connector versão 1.4.2 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-256">This task is not required for Cloud Connector versions 1.4.2 and later.</span></span> 

<span data-ttu-id="7cf1f-257">A conta CceService é criada durante a implantação do Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-257">The CceService account is created during the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="7cf1f-258">Ele executa o serviço de gerenciamento do Cloud Connector e requer permissão para desinstalar o cloudconnector. msi.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-258">It runs the Cloud Connector Management Service and requires permission to uninstall the cloudconnector.msi.</span></span> <span data-ttu-id="7cf1f-259">Você deve alterar a configuração da política de grupo na máquina host do Cloud Connector para especificar que o registro do usuário não deve ser descarregado quando o usuário se desconecta.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-259">You must change the group policy setting on the Cloud Connector host machine to specify that the user registry should not be unloaded when the user logs off.</span></span> <span data-ttu-id="7cf1f-260">Siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="7cf1f-260">Follow the steps below:</span></span>

### <a name="to-change-the-group-policy-setting"></a><span data-ttu-id="7cf1f-261">Para alterar a configuração da Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="7cf1f-261">To change the Group Policy setting</span></span>

1. <span data-ttu-id="7cf1f-262">Abra o **Editor de política de grupo** executando gpedit. msc.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-262">Open the **Group Policy Editor** by running gpedit.msc.</span></span>

2. <span data-ttu-id="7cf1f-263">No **Editor de Política de Grupo**, navegue até Modelos Administrativos > Sistema > Perfil de Usuário > Não descarregar forçosamente o Registro do usuário no logoff do usuário. </span><span class="sxs-lookup"><span data-stu-id="7cf1f-263">In the **Group Policy Editor**, navigate to Administrative Templates > System > UserProfile > Do not forcefully unload the user registry at user logoff.</span></span> 

3. <span data-ttu-id="7cf1f-264">Defina seu valor como **Enabled**.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-264">Set its value to **Enabled**.</span></span>

## <a name="set-up-your-office-365-tenant"></a><span data-ttu-id="7cf1f-265">Configure o locatário do Office 365</span><span class="sxs-lookup"><span data-stu-id="7cf1f-265">Set up your Office 365 tenant</span></span>

<span data-ttu-id="7cf1f-266">É necessário um locatário do Office 365 com o Skype for Business Online e o sistema telefônico no Office 365.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-266">An Office 365 tenant with Skype for Business Online and Phone System in Office 365 is required.</span></span> <span data-ttu-id="7cf1f-267">Certifique-se de que seu locatário esteja configurado e configurado antes de tentar usar o conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-267">Make sure your tenant is set up and configured before attempting to use Cloud Connector.</span></span>

<span data-ttu-id="7cf1f-268">Algumas etapas de configuração do Office 365 exigem que você use o PowerShell Remote locatário (TRPS) para configurar seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-268">Some Office 365 setup steps require you to use Tenant Remote PowerShell (TRPS) to configure your Office 365 tenant.</span></span> <span data-ttu-id="7cf1f-269">**Isso deve ser instalado no servidor host.**</span><span class="sxs-lookup"><span data-stu-id="7cf1f-269">**This should be installed on the host server.**</span></span> <span data-ttu-id="7cf1f-270">Você pode baixar o módulo Skype for Business online para PowerShell de: [Skype for Business Online, módulo do Windows PowerShell](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="7cf1f-270">You can download the Skype for Business Online module for PowerShell from: [Skype for Business Online, Windows PowerShell Module](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="7cf1f-271">Crie uma conta de administrador dedicada do Skype for Business para o gerenciamento online do conector de nuvem, por exemplo, CceOnlineManagmentAdministrator.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-271">Create a dedicated Skype for Business administrator account for Cloud Connector online management, for example CceOnlineManagmentAdministrator.</span></span> <span data-ttu-id="7cf1f-272">Essa conta será usada pelo dispositivo para adicionar ou remover dispositivos, habilitar ou desabilitar a atualização automática do sistema operacional, habilitar ou desabilitar a atualização automática de binários.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-272">This account will be used by appliance to add or remove appliance, enable or disable automatic OS update, enable or disable automatic binary update.</span></span> <span data-ttu-id="7cf1f-273">Defina a senha dessa conta como nunca expirar, assim não será necessário alterá-la para o serviço sempre que ela expirar.</span><span class="sxs-lookup"><span data-stu-id="7cf1f-273">Set the password for this account to never expire so that you do not need to change it for the service each time it expires.</span></span>


