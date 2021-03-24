---
title: Configurar a autenticação de dois fatores no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: 'Resumo: Configure a autenticação de dois fatores no Skype for Business Server.'
ms.openlocfilehash: 8651be3fbc07bb890637bc8d1c7c99a827d1ea1e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096817"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="dc24d-103">Configurar a autenticação de dois fatores no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dc24d-103">Configure two-factor authentication in Skype for Business Server</span></span>

<span data-ttu-id="dc24d-104">**Resumo:** Configure a autenticação de dois fatores no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="dc24d-104">**Summary:** Configure two-factor authentication in Skype for Business Server.</span></span>

<span data-ttu-id="dc24d-105">As seções a seguir descrevem as etapas necessárias para configurar a autenticação de dois fatores para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="dc24d-105">The following sections describe the steps necessary to configure two-factor authentication for your deployment.</span></span> <span data-ttu-id="dc24d-106">Para obter mais informações sobre a autenticação de dois fatores, consulte Habilitando a autenticação [multifatório do Office 365](https://go.microsoft.com/fwlink/p/?LinkId=313332)para administradores online - Postagem de Usuário de Grade.</span><span class="sxs-lookup"><span data-stu-id="dc24d-106">For more information about Two-factor authentication, see [Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).</span></span>

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="dc24d-107">Configurar uma Autoridade de Certificado Raiz da Empresa para dar suporte à autenticação de cartão inteligente</span><span class="sxs-lookup"><span data-stu-id="dc24d-107">Configure an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="dc24d-108">As etapas a seguir descrevem como configurar uma AC Raiz da Empresa para dar suporte à Autenticação de Cartão Inteligente:</span><span class="sxs-lookup"><span data-stu-id="dc24d-108">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

<span data-ttu-id="dc24d-109">Para obter informações sobre como instalar uma AC raiz da empresa, consulte [Install an Enterprise Root Certification Authority](/previous-versions/windows/it-pro/windows-server-2003/cc776709(v=ws.10)).</span><span class="sxs-lookup"><span data-stu-id="dc24d-109">For information on how to install an Enterprise Root CA, see [Install an Enterprise Root Certification Authority](/previous-versions/windows/it-pro/windows-server-2003/cc776709(v=ws.10)).</span></span>

1. <span data-ttu-id="dc24d-110">Faça logoff no computador da AC Empresarial usando uma conta de Administrador de Domínio.</span><span class="sxs-lookup"><span data-stu-id="dc24d-110">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="dc24d-111">Iniciar o System Manager e verificar se a função de Registro da Web da Autoridade de Certificação está instalada.</span><span class="sxs-lookup"><span data-stu-id="dc24d-111">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3. <span data-ttu-id="dc24d-112">No menu **Ferramentas Administrativas,** abra o console de gerenciamento **da Autoridade** de Certificação.</span><span class="sxs-lookup"><span data-stu-id="dc24d-112">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4. <span data-ttu-id="dc24d-113">No painel De navegação, expanda **a Autoridade de Certificação**.</span><span class="sxs-lookup"><span data-stu-id="dc24d-113">In the Navigation pane, expand **Certification Authority**.</span></span>

5. <span data-ttu-id="dc24d-114">Clique com o botão direito do mouse em Modelos **de Certificados,** selecione **Novo** e, em seguida, selecione Modelo de Certificado **para Emitir**.</span><span class="sxs-lookup"><span data-stu-id="dc24d-114">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6. <span data-ttu-id="dc24d-115">Selecione **Agente de Registro,** **Usuário Smartcard** e **Logon do Smartcard.**</span><span class="sxs-lookup"><span data-stu-id="dc24d-115">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7. <span data-ttu-id="dc24d-116">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc24d-116">Click **OK**.</span></span>

8. <span data-ttu-id="dc24d-117">Clique com o botão **direito do mouse em Modelos de Certificado.**</span><span class="sxs-lookup"><span data-stu-id="dc24d-117">Right click on **Certificate Templates**.</span></span>

9. <span data-ttu-id="dc24d-118">Selecione **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="dc24d-118">Select **Manage**.</span></span>

10. <span data-ttu-id="dc24d-119">Abra as propriedades do modelo de usuário smartcard.</span><span class="sxs-lookup"><span data-stu-id="dc24d-119">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="dc24d-120">Clique na guia **Segurança.**</span><span class="sxs-lookup"><span data-stu-id="dc24d-120">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="dc24d-121">Altere as permissões da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="dc24d-121">Change the permissions as follows:</span></span>

    - <span data-ttu-id="dc24d-122">Adicionar contas de AD de usuário individuais com permissões de Leitura/Registro (Permitir) ou</span><span class="sxs-lookup"><span data-stu-id="dc24d-122">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="dc24d-123">Adicionar um grupo de segurança que contém usuários de cartão inteligente com permissões de Leitura/Registro (Permitir) ou</span><span class="sxs-lookup"><span data-stu-id="dc24d-123">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="dc24d-124">Adicionar o grupo Usuários de Domínio com permissões de Leitura/Registro (Permitir)</span><span class="sxs-lookup"><span data-stu-id="dc24d-124">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

## <a name="configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="dc24d-125">Configurar o Windows 8 para Cartões Inteligentes Virtuais</span><span class="sxs-lookup"><span data-stu-id="dc24d-125">Configure Windows 8 for Virtual Smart Cards</span></span>

<span data-ttu-id="dc24d-126">Um fator a ser considerado ao implantar a autenticação de dois fatores e a tecnologia de cartão inteligente é o custo da implementação.</span><span class="sxs-lookup"><span data-stu-id="dc24d-126">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="dc24d-127">O Windows 8 fornece vários novos recursos de segurança e um dos novos recursos mais interessantes é o suporte a cartões inteligentes virtuais.</span><span class="sxs-lookup"><span data-stu-id="dc24d-127">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="dc24d-128">Para computadores equipados com um chip TPM (Trusted Platform Module) que atenda à especificação versão 1.2, as organizações agora podem obter os benefícios do logon de cartão inteligente sem fazer investimentos adicionais em hardware.</span><span class="sxs-lookup"><span data-stu-id="dc24d-128">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="dc24d-129">Para obter mais informações, consulte [Using Virtual Smart Cards with Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).</span><span class="sxs-lookup"><span data-stu-id="dc24d-129">For more information, see [Using Virtual Smart Cards with Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).</span></span>

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="dc24d-130">Para configurar o Windows 8 para cartões inteligentes virtuais</span><span class="sxs-lookup"><span data-stu-id="dc24d-130">To Configure Windows 8 for Virtual Smart Cards</span></span>

1. <span data-ttu-id="dc24d-131">Faça logoff no computador Windows 8 usando as credenciais de um usuário habilitado para Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="dc24d-131">Log in to the Windows 8 computer using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="dc24d-132">Na tela inicial do Windows 8, mova o cursor para o canto inferior direito da tela.</span><span class="sxs-lookup"><span data-stu-id="dc24d-132">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3. <span data-ttu-id="dc24d-133">Selecione a **opção Pesquisar** e, em seguida, pesquise prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="dc24d-133">Select the **Search** option, and then search forCommand Prompt.</span></span>

4. <span data-ttu-id="dc24d-134">Clique com o **botão direito do** mouse no Prompt de Comando e selecione Executar como **Administrador**.</span><span class="sxs-lookup"><span data-stu-id="dc24d-134">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5. <span data-ttu-id="dc24d-135">Abra o console de Gerenciamento do Módulo de Plataforma Confiável (TPM) executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="dc24d-135">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>

  ```console
  Tpm.msc
  ```

6. <span data-ttu-id="dc24d-136">No console de gerenciamento do TPM, verifique se sua versão de especificação do TPM é pelo menos 1,2</span><span class="sxs-lookup"><span data-stu-id="dc24d-136">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>

    > [!NOTE]
    > <span data-ttu-id="dc24d-137">Se você receber uma caixa de diálogo informando que não é possível encontrar um TPM (Compatible Trust Platform Module), verifique se o computador tem um módulo TPM compatível e se ele está habilitado no BIOS do sistema.</span><span class="sxs-lookup"><span data-stu-id="dc24d-137">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

7. <span data-ttu-id="dc24d-138">Fechar o console de gerenciamento do TPM</span><span class="sxs-lookup"><span data-stu-id="dc24d-138">Close the TPM management console</span></span>

8. <span data-ttu-id="dc24d-139">No prompt de comando, crie um novo cartão inteligente virtual usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="dc24d-139">From the command prompt, create a new virtual smart card using the following command:</span></span>

  ```console
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > <span data-ttu-id="dc24d-140">Para fornecer um valor pin personalizado ao criar o cartão inteligente virtual, use o prompt /pin em vez disso.</span><span class="sxs-lookup"><span data-stu-id="dc24d-140">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

9. <span data-ttu-id="dc24d-141">No prompt de comando, abra o console de Gerenciamento de Computador executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="dc24d-141">From the command prompt, open the Computer Management console by running the following command:</span></span>

  ```console
  CompMgmt.msc
  ```

10. <span data-ttu-id="dc24d-142">No console de Gerenciamento de Computador, selecione **Gerenciamento de Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="dc24d-142">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="dc24d-143">Expanda **leitores de cartão inteligente**.</span><span class="sxs-lookup"><span data-stu-id="dc24d-143">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="dc24d-144">Verifique se o novo leitor de cartão inteligente virtual foi criado com êxito.</span><span class="sxs-lookup"><span data-stu-id="dc24d-144">Verify that the new virtual smart card reader has been created successfully.</span></span>

## <a name="enroll-users-for-smart-card-authentication"></a><span data-ttu-id="dc24d-145">Registrar usuários para autenticação de cartão inteligente</span><span class="sxs-lookup"><span data-stu-id="dc24d-145">Enroll users for smart card authentication</span></span>

<span data-ttu-id="dc24d-146">Geralmente, há dois métodos para registrar usuários para autenticação de cartão inteligente.</span><span class="sxs-lookup"><span data-stu-id="dc24d-146">There are generally two methods for enrolling users for smart card authentication.</span></span> <span data-ttu-id="dc24d-147">O método mais fácil envolve fazer com que os usuários se inscrevam diretamente para autenticação de cartão inteligente usando o registro da Web, enquanto o método mais complexo envolve o uso de um agente de registro.</span><span class="sxs-lookup"><span data-stu-id="dc24d-147">The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent.</span></span> <span data-ttu-id="dc24d-148">Este tópico se concentra no auto-registro para certificados de cartão inteligente.</span><span class="sxs-lookup"><span data-stu-id="dc24d-148">This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="dc24d-149">Para obter mais informações sobre o registro em nome dos usuários como agente de registro, consulte [Enroll for Certificates on Behalf of Other Users](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc770802(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="dc24d-149">For more information on enrolling on behalf of users as an enrollment agent, see [Enroll for Certificates on Behalf of Other Users](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc770802(v=ws.11)).</span></span>

### <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="dc24d-150">Para registrar usuários para autenticação de cartão inteligente</span><span class="sxs-lookup"><span data-stu-id="dc24d-150">To Enroll Users for Smart Card Authentication</span></span>

1. <span data-ttu-id="dc24d-151">Faça logoff na estação de trabalho do Windows 8 usando as credenciais de um usuário habilitado para Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="dc24d-151">Log in to the Windows 8 workstation using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="dc24d-152">Iniciar o Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="dc24d-152">Launch Internet Explorer.</span></span>

3. <span data-ttu-id="dc24d-153">Navegue até a página **Registro da Web da** Autoridade de Certificação (por exemplo, https://MyCA.contoso.com/certsrv) .</span><span class="sxs-lookup"><span data-stu-id="dc24d-153">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>

    > [!NOTE]
    > <span data-ttu-id="dc24d-154">Se você estiver usando o Internet Explorer 10, talvez seja necessário exibir este site no Modo de Compatibilidade.</span><span class="sxs-lookup"><span data-stu-id="dc24d-154">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

4. <span data-ttu-id="dc24d-155">Na Página **de Boas-vindas,** selecione **Solicitar um certificado**.</span><span class="sxs-lookup"><span data-stu-id="dc24d-155">On the **Welcome** Page, select **Request a certificate**.</span></span>

5. <span data-ttu-id="dc24d-156">Em seguida, selecione **Solicitação Avançada**.</span><span class="sxs-lookup"><span data-stu-id="dc24d-156">Next, select **Advanced Request**.</span></span>

6. <span data-ttu-id="dc24d-157">Selecione **Criar e enviar uma solicitação para esta CA**.</span><span class="sxs-lookup"><span data-stu-id="dc24d-157">Select **Create and submit a request to this CA**.</span></span>

7. <span data-ttu-id="dc24d-158">Selecione **Usuário de Cartão Inteligente** na seção Modelo **de** Certificado e conclua a solicitação de certificado avançada com os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="dc24d-158">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>

  - <span data-ttu-id="dc24d-159">**Opções de chave** confirmam as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="dc24d-159">**Key Options** confirm he following settings:</span></span>

    - <span data-ttu-id="dc24d-160">Selecione o **botão de opção Criar novo conjunto de** chaves</span><span class="sxs-lookup"><span data-stu-id="dc24d-160">Select the **Create new key set** radio button</span></span>

    - <span data-ttu-id="dc24d-161">Para **CSP,** selecione **Provedor de Criptografia de Cartão Inteligente da Microsoft Base**</span><span class="sxs-lookup"><span data-stu-id="dc24d-161">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>

    - <span data-ttu-id="dc24d-162">Para **Uso de Chave,** selecione **Exchange** (essa é a única opção disponível).</span><span class="sxs-lookup"><span data-stu-id="dc24d-162">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>

    - <span data-ttu-id="dc24d-163">Para **Tamanho da Chave**, insira 2048</span><span class="sxs-lookup"><span data-stu-id="dc24d-163">For **Key Size**, enter 2048</span></span>

    - <span data-ttu-id="dc24d-164">Confirme se **o nome do contêiner de chave automática** está selecionado</span><span class="sxs-lookup"><span data-stu-id="dc24d-164">Confirm that **Automatic key container name** is selected</span></span>

    - <span data-ttu-id="dc24d-165">Deixe as outras caixas desmarcadas.</span><span class="sxs-lookup"><span data-stu-id="dc24d-165">Leave the other boxes unchecked.</span></span>

  - <span data-ttu-id="dc24d-166">Em **Opções Adicionais,** confirme os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="dc24d-166">Under **Additional Options** confirm the following values:</span></span>

    - <span data-ttu-id="dc24d-167">Para **Formato de Solicitação,** **selecione CMC**.</span><span class="sxs-lookup"><span data-stu-id="dc24d-167">For **Request Format** select **CMC**.</span></span>

    - <span data-ttu-id="dc24d-168">Para **Algoritmo de Hash,** **selecione sha1**.</span><span class="sxs-lookup"><span data-stu-id="dc24d-168">For **Hash Algorithm** select **sha1**.</span></span>

    - <span data-ttu-id="dc24d-169">Para **Nome Amigável,** enterSmardcard Certificate.</span><span class="sxs-lookup"><span data-stu-id="dc24d-169">For **Friendly Name** enterSmardcard Certificate.</span></span>

8. <span data-ttu-id="dc24d-170">Se você estiver usando um leitor de cartão inteligente físico, insira o cartão inteligente no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dc24d-170">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9. <span data-ttu-id="dc24d-171">Clique **em Enviar** para enviar a solicitação de certificado.</span><span class="sxs-lookup"><span data-stu-id="dc24d-171">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="dc24d-172">Quando solicitado, insira o PIN usado para criar o cartão inteligente virtual.</span><span class="sxs-lookup"><span data-stu-id="dc24d-172">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dc24d-173">O valor padrão de PIN de cartão inteligente virtual é '12345678'.</span><span class="sxs-lookup"><span data-stu-id="dc24d-173">The default virtual smart card PIN value is '12345678'.</span></span>

11. <span data-ttu-id="dc24d-174">Depois que o certificado for emitido, clique em **Instalar esse certificado para** concluir o processo de registro.</span><span class="sxs-lookup"><span data-stu-id="dc24d-174">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="dc24d-175">Se sua solicitação de certificado falhar com o erro "Este navegador da Web não dá suporte à geração de solicitações de certificado", há três maneiras possíveis de resolver o problema:</span><span class="sxs-lookup"><span data-stu-id="dc24d-175">If your certificate request fails with the error "This Web browser does not support the generation of certificate requests," there are three possible ways to resolve the issue:</span></span>

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a><span data-ttu-id="dc24d-176">Configurar os Serviços de Federação do Active Directory (AD FS 2.0)</span><span class="sxs-lookup"><span data-stu-id="dc24d-176">Configure Active Directory Federation Services (AD FS 2.0)</span></span>

<span data-ttu-id="dc24d-177">A seção a seguir descreve como configurar os Serviços de Federação do Active Directory (AD FS 2.0) para dar suporte à autenticação multifacional.</span><span class="sxs-lookup"><span data-stu-id="dc24d-177">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="dc24d-178">Para obter informações sobre como instalar o AD FS 2.0, consulte [AD FS 2.0 Passo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10))a passo e Como Guias .</span><span class="sxs-lookup"><span data-stu-id="dc24d-178">For information on how to install AD FS 2.0, see [AD FS 2.0 Step-by-Step and How To Guides](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10)).</span></span>

> [!NOTE]
> <span data-ttu-id="dc24d-179">Ao instalar o AD FS 2.0, não use o Gerenciador do Windows Server para adicionar a função Serviços de Federação do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dc24d-179">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="dc24d-180">Em vez disso, baixe e instale o pacote RTW dos Serviços de [Federação do Active Directory 2.0](https://go.microsoft.com/fwlink/p/?LinkId=313375).</span><span class="sxs-lookup"><span data-stu-id="dc24d-180">Instead, download and install the [Active Directory Federation Services 2.0 RTW package](https://go.microsoft.com/fwlink/p/?LinkId=313375).</span></span>

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a><span data-ttu-id="dc24d-181">Para configurar o AD FS para autenticação de dois fatores</span><span class="sxs-lookup"><span data-stu-id="dc24d-181">To configure AD FS for two-factor Authentication</span></span>

1. <span data-ttu-id="dc24d-182">Faça logoff no computador do AD FS 2.0 usando uma conta de Administrador de Domínio.</span><span class="sxs-lookup"><span data-stu-id="dc24d-182">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="dc24d-183">Inicie o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dc24d-183">Start Windows PowerShell.</span></span>

3. <span data-ttu-id="dc24d-184">Na linha Windows PowerShell de comando, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="dc24d-184">From the Windows PowerShell command-line, run the following command:</span></span>

  ```PowerShell
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. <span data-ttu-id="dc24d-185">Estabeleça uma parceria com cada servidor que será habilitado para autenticação passiva executando o seguinte comando, substituindo o nome do servidor específico da sua implantação:</span><span class="sxs-lookup"><span data-stu-id="dc24d-185">Establish a partnership with each server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>

  ```PowerShell
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. <span data-ttu-id="dc24d-186">No menu Ferramentas Administrativas, iniciar o console de Gerenciamento do AD FS 2.0.</span><span class="sxs-lookup"><span data-stu-id="dc24d-186">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6. <span data-ttu-id="dc24d-187">Expanda **relações de confiança**  >  **Confiando confianças de terceiros.**</span><span class="sxs-lookup"><span data-stu-id="dc24d-187">Expand **Trust Relationships** > **Relying Party Trusts**.</span></span>

7. <span data-ttu-id="dc24d-188">Verifique se uma nova confiança foi criada para seu Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="dc24d-188">Verify that a new trust has been created for your Skype for Business Server.</span></span>

8. <span data-ttu-id="dc24d-189">Crie e atribua uma Regra de Autorização de Emissão para sua confiança de parte confiável usando Windows PowerShell executando os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="dc24d-189">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```PowerShell
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. <span data-ttu-id="dc24d-190">Crie e atribua uma Regra de Transformação de Emissão para sua confiança de parte confiável usando Windows PowerShell executando os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="dc24d-190">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```PowerShell
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. <span data-ttu-id="dc24d-191">No console de Gerenciamento do AD FS 2.0, clique com o botão direito do mouse em sua confiança de parte confiável e selecione **Editar Regras de Declaração.**</span><span class="sxs-lookup"><span data-stu-id="dc24d-191">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="dc24d-192">Selecione a **guia Regras de Autorização** de Emissão e verifique se a nova regra de autorização foi criada com êxito.</span><span class="sxs-lookup"><span data-stu-id="dc24d-192">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="dc24d-193">Selecione a **guia Regras de Transformação de Emissão** e verifique se a nova regra de transformação foi criada com êxito.</span><span class="sxs-lookup"><span data-stu-id="dc24d-193">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="dc24d-194">Configurando o AD FS 2.0 para dar suporte à autenticação do cliente</span><span class="sxs-lookup"><span data-stu-id="dc24d-194">Configuring AD FS 2.0 to support client authentication</span></span>

<span data-ttu-id="dc24d-195">Há dois tipos de autenticação possíveis que podem ser configurados para permitir que o AD FS 2.0 suporte a autenticação usando cartões inteligentes:</span><span class="sxs-lookup"><span data-stu-id="dc24d-195">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

- <span data-ttu-id="dc24d-196">Autenticação baseada em formulários (FBA)</span><span class="sxs-lookup"><span data-stu-id="dc24d-196">Forms-based authentication (FBA)</span></span>

- <span data-ttu-id="dc24d-197">Autenticação do cliente de segurança de camada de transporte</span><span class="sxs-lookup"><span data-stu-id="dc24d-197">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="dc24d-198">Usando a autenticação baseada em formulários, você pode desenvolver uma página da Web que permite aos usuários autenticar usando seu nome de usuário/senha ou usando seu cartão inteligente e PIN.</span><span class="sxs-lookup"><span data-stu-id="dc24d-198">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="dc24d-199">Este tópico se concentra em como implementar a Autenticação do Cliente de Segurança de Camada de Transporte com o AD FS 2.0.</span><span class="sxs-lookup"><span data-stu-id="dc24d-199">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="dc24d-200">Para obter mais informações sobre tipos de autenticação do AD FS 2.0, consulte [AD FS 2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span><span class="sxs-lookup"><span data-stu-id="dc24d-200">For more information about AD FS 2.0 authentication types, see [AD FS 2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span></span>

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="dc24d-201">Para configurar o AD FS 2.0 para dar suporte à autenticação do cliente</span><span class="sxs-lookup"><span data-stu-id="dc24d-201">To Configure AD FS 2.0 to Support Client Authentication</span></span>

1. <span data-ttu-id="dc24d-202">Faça logoff no computador do AD FS 2.0 usando uma conta de Administrador de Domínio.</span><span class="sxs-lookup"><span data-stu-id="dc24d-202">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="dc24d-203">Iniciar o Windows Explorer.</span><span class="sxs-lookup"><span data-stu-id="dc24d-203">Launch Windows Explorer.</span></span>

3. <span data-ttu-id="dc24d-204">Navegue até C:\inetpub\adfs\ls</span><span class="sxs-lookup"><span data-stu-id="dc24d-204">Browse to C:\inetpub\adfs\ls</span></span>

4. <span data-ttu-id="dc24d-205">Faça uma cópia de backup do arquivo web.config existente.</span><span class="sxs-lookup"><span data-stu-id="dc24d-205">Make a backup copy of the existing web.config file.</span></span>

5. <span data-ttu-id="dc24d-206">Abra o arquivo web.config existente usando o Bloco de Notas.</span><span class="sxs-lookup"><span data-stu-id="dc24d-206">Open the existing web.config file using Notepad.</span></span>

6. <span data-ttu-id="dc24d-207">Na barra menu, selecione **Editar** e selecione **Encontrar**.</span><span class="sxs-lookup"><span data-stu-id="dc24d-207">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7. <span data-ttu-id="dc24d-208">Pesquise \<localAuthenticationTypes\> por .</span><span class="sxs-lookup"><span data-stu-id="dc24d-208">Search for \<localAuthenticationTypes\>.</span></span>

    <span data-ttu-id="dc24d-209">Observe que há quatro tipos de autenticação listados, um por linha.</span><span class="sxs-lookup"><span data-stu-id="dc24d-209">Note that there are four authentication types listed, one per line.</span></span>

8. <span data-ttu-id="dc24d-210">Mova a linha que contém o tipo de autenticação TLSClient para a parte superior da lista na seção.</span><span class="sxs-lookup"><span data-stu-id="dc24d-210">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9. <span data-ttu-id="dc24d-211">Salve e feche o arquivo web.config arquivo.</span><span class="sxs-lookup"><span data-stu-id="dc24d-211">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="dc24d-212">Iniciar um Prompt de Comando com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="dc24d-212">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="dc24d-213">Reinicie o IIS executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="dc24d-213">Restart IIS by running the following command:</span></span>

  ```console
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a><span data-ttu-id="dc24d-214">Configurando a autenticação passiva do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dc24d-214">Configuring Skype for Business Server passive authentication</span></span>

<span data-ttu-id="dc24d-215">A seção a seguir descreve como configurar o Skype for Business Server para dar suporte à autenticação passiva.</span><span class="sxs-lookup"><span data-stu-id="dc24d-215">The following section describes how to configure Skype for Business Server to support passive authentication.</span></span> <span data-ttu-id="dc24d-216">Depois de habilitado, os usuários habilitados para autenticação de dois fatores serão obrigados a usar um cartão inteligente físico ou virtual e um PIN válido para entrar usando o cliente skype for Business.</span><span class="sxs-lookup"><span data-stu-id="dc24d-216">Once enabled, users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Skype for Business client.</span></span>

> [!NOTE]
> <span data-ttu-id="dc24d-217">É altamente recomendável que os clientes habilitam a autenticação passiva para Registrador e Serviços Web no nível de serviço.</span><span class="sxs-lookup"><span data-stu-id="dc24d-217">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level.</span></span> <span data-ttu-id="dc24d-218">Se a autenticação passiva estiver habilitada para o Registrador e os Serviços Web no nível global, provavelmente resultará em falhas de autenticação em toda a organização para usuários que não estão fazendo o contato com o cliente da área de trabalho com suporte.</span><span class="sxs-lookup"><span data-stu-id="dc24d-218">If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the supported desktop client.</span></span>

### <a name="web-service-configuration"></a><span data-ttu-id="dc24d-219">Configuração do Serviço Web</span><span class="sxs-lookup"><span data-stu-id="dc24d-219">Web Service Configuration</span></span>

<span data-ttu-id="dc24d-220">As etapas a seguir descrevem como criar uma configuração de serviço Web personalizada para os servidores Directors, Pools Corporativos e Standard Edition que serão habilitados para autenticação passiva.</span><span class="sxs-lookup"><span data-stu-id="dc24d-220">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-web-service-configuration"></a><span data-ttu-id="dc24d-221">Para criar uma configuração de serviço Web personalizada</span><span class="sxs-lookup"><span data-stu-id="dc24d-221">To create a custom web service configuration</span></span>

1. <span data-ttu-id="dc24d-222">Faça logoff no servidor front-end do Skype for Business Server usando uma conta de administrador do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="dc24d-222">Log in to your Skype for Business Server Front End server using a Skype for Business administrator account.</span></span>

2. <span data-ttu-id="dc24d-223">Iniciar o Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="dc24d-223">Launch the Skype for Business Server Management Shell.</span></span>

3. <span data-ttu-id="dc24d-224">Na linha de comando Shell de Gerenciamento do Skype for Business Server, crie uma nova configuração de Serviço Web para cada servidor Diretor, Pool Empresarial e Standard Edition que será habilitado para autenticação passiva executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="dc24d-224">From the Skype for Business Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>

  ```PowerShell
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > <span data-ttu-id="dc24d-225">O valor do FQDN WsFedPassiveMetadataUri é o Nome do Serviço de Federação do servidor do AD FS 2.0.</span><span class="sxs-lookup"><span data-stu-id="dc24d-225">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server.</span></span> <span data-ttu-id="dc24d-226">O valor Nome do Serviço de Federação pode ser encontrado no Console de Gerenciamento do AD FS 2.0 clicando com o botão direito do mouse em **Serviço** no painel de navegação e selecionando Editar Propriedades do Serviço de **Federação.**</span><span class="sxs-lookup"><span data-stu-id="dc24d-226">The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on **Service** from the navigation pane and then selecting **Edit Federation Service Properties**.</span></span>

4. <span data-ttu-id="dc24d-227">Verifique se os valores UseWsFedPassiveAuth e WsFedPassiveMetadataUri foram definidos corretamente executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="dc24d-227">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>

  ```PowerShell
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. <span data-ttu-id="dc24d-228">Para clientes, Autenticação Passiva é o método de autenticação menos preferencial para autenticação de webticket.</span><span class="sxs-lookup"><span data-stu-id="dc24d-228">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="dc24d-229">Para todos os servidores Diretores, Pools Corporativos e Standard Edition que serão habilitados para autenticação passiva, todos os outros tipos de autenticação devem ser desabilitados no Skype for Business Web Services executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="dc24d-229">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Skype for Business Web Services by running the following cmdlet:</span></span>

  ```PowerShell
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. <span data-ttu-id="dc24d-230">Verifique se todos os outros tipos de autenticação foram desabilitados com êxito executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="dc24d-230">Verify that all other authentication types have been successfully disabled by running the following cmdlet:</span></span>

  ```PowerShell
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a><span data-ttu-id="dc24d-231">Configuração de Proxy</span><span class="sxs-lookup"><span data-stu-id="dc24d-231">Proxy Configuration</span></span>

<span data-ttu-id="dc24d-232">Quando a autenticação de certificado estiver desabilitada para o Skype for Business Web Services, o cliente skype for Business usará um tipo de autenticação menos preferencial, como Kerberos ou NTLM, para autenticar no serviço Registrador.</span><span class="sxs-lookup"><span data-stu-id="dc24d-232">When certificate authentication is disabled for Skype for Business Web Services, the Skype for Business client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="dc24d-233">A autenticação de certificado ainda é necessária para permitir que o cliente recupere uma webticket, no entanto, Kerberos e NTLM devem ser desabilitados para o serviço Registrador.</span><span class="sxs-lookup"><span data-stu-id="dc24d-233">Certificate authentication is still needed to allow the client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="dc24d-234">As etapas a seguir descrevem como criar uma configuração de proxy personalizada para pools de borda, pools corporativos e servidores Standard Edition que serão habilitados para autenticação passiva.</span><span class="sxs-lookup"><span data-stu-id="dc24d-234">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-proxy-configuration"></a><span data-ttu-id="dc24d-235">Para criar uma configuração de proxy personalizada</span><span class="sxs-lookup"><span data-stu-id="dc24d-235">To create a custom proxy configuration</span></span>

1. <span data-ttu-id="dc24d-236">Na linha de comando Shell de Gerenciamento do Skype for Business Server, crie uma nova configuração de proxy para cada Pool de Borda do Skype for Business Server, Pool empresarial e servidor Standard Edition que será habilitado para autenticação passiva executando os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="dc24d-236">From the Skype for Business Server Management Shell command-line, create a new proxy configuration for each Skype for Business Server Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. <span data-ttu-id="dc24d-237">Verifique se todos os outros tipos de autenticação de proxy foram desabilitados com êxito executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="dc24d-237">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>

  ```PowerShell
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a><span data-ttu-id="dc24d-238">Confira também</span><span class="sxs-lookup"><span data-stu-id="dc24d-238">See also</span></span>

[<span data-ttu-id="dc24d-239">Gerenciar autenticação de dois fatores no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dc24d-239">Manage two-factor authentication in Skype for Business Server</span></span>](two-factor-authentication.md)

[<span data-ttu-id="dc24d-240">Usar autenticação de dois fatores com cliente Skype for Business e Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dc24d-240">Use two-factor authentication with Skype for Business client and Skype for Business Server</span></span>](use-two-factor.md)