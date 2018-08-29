---
title: Configurar a autenticação de dois fatores no Skype para Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: 'Resumo: Configure a autenticação de dois fatores no Skype para Business Server.'
ms.openlocfilehash: 4fc8791cd7459ecea89bb8101b2c1a488b6eace2
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23250798"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="e9ec1-103">Configurar a autenticação de dois fatores no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="e9ec1-103">Configure two-factor authentication in Skype for Business Server</span></span>

<span data-ttu-id="e9ec1-104">**Resumo:** Configure a autenticação de dois fatores no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-104">**Summary:** Configure two-factor authentication in Skype for Business Server.</span></span>

<span data-ttu-id="e9ec1-105">As seções a seguir descrevem as etapas necessárias para configurar a autenticação de duas etapas para sua implementação.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-105">The following sections describe the steps necessary to configure two-factor authentication for your deployment.</span></span> <span data-ttu-id="e9ec1-106">Para obter mais informações sobre a autenticação de dois fatores, consulte [Habilitando o Office 365 a autenticação multifator para administradores online - Post do usuário de grade](https://go.microsoft.com/fwlink/p/?LinkId=313332).</span><span class="sxs-lookup"><span data-stu-id="e9ec1-106">For more information about Two-factor authentication, see [Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).</span></span>

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="e9ec1-107">Configuração de uma Autoridade de Certificação Raiz Corporativa para dar suporte à Autenticação de Cartão Inteligente</span><span class="sxs-lookup"><span data-stu-id="e9ec1-107">Configure an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="e9ec1-108">As seguintes etapas descrevem como configurar uma CA Raiz Corporativa para dar suporte à Autenticação de Cartão Inteligente:</span><span class="sxs-lookup"><span data-stu-id="e9ec1-108">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

<span data-ttu-id="e9ec1-109">Para obter informações sobre como instalar uma autoridade de certificação raiz corporativa, consulte [instalar uma autoridade de certificação raiz corporativa](https://go.microsoft.com/fwlink/p/?LinkID=313364).</span><span class="sxs-lookup"><span data-stu-id="e9ec1-109">For information on how to install an Enterprise Root CA, see [Install an Enterprise Root Certification Authority](https://go.microsoft.com/fwlink/p/?LinkID=313364).</span></span>

1. <span data-ttu-id="e9ec1-110">Faça o login no computador da AC corporativa utilizando uma conta de Administrador de Domínio.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-110">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="e9ec1-111">Inicie o Gerenciador de Sistema e verifique se a função de Registro da Web da Autoridade de Certificação está instalada.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-111">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3. <span data-ttu-id="e9ec1-112">No menu **Ferramentas Administrativas**, abra o console de gerenciamento da **Autoridade de Certificação**.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-112">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4. <span data-ttu-id="e9ec1-113">No painel de Navegação, expanda **Autoridade de Certificação**.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-113">In the Navigation pane, expand **Certification Authority**.</span></span>

5. <span data-ttu-id="e9ec1-114">Clique com o botão direito do mouse em **Modelos de Certificado**, selecione **Novo** e, em seguida, selecione **Modelo de Certificação para Emissão**.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-114">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6. <span data-ttu-id="e9ec1-115">Selecione **Agente de Registro**, **Usuário do Cartão Inteligente** e **Logon do Cartão Inteligente**.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-115">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7. <span data-ttu-id="e9ec1-116">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-116">Click **OK**.</span></span>

8. <span data-ttu-id="e9ec1-117">Clique com o botão direito em **Modelos de Certificado**.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-117">Right click on **Certificate Templates**.</span></span>

9. <span data-ttu-id="e9ec1-118">Selecione **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-118">Select **Manage**.</span></span>

10. <span data-ttu-id="e9ec1-119">Abra as propriedades do modelo do Usuário do Cartão Inteligente.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-119">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="e9ec1-120">Clique na guia **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-120">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="e9ec1-121">Altere as permissões da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="e9ec1-121">Change the permissions as follows:</span></span>

    - <span data-ttu-id="e9ec1-122">Adicione contas de AD de usuários individuais com permissões para Ler/Registrar (Permitir) ou</span><span class="sxs-lookup"><span data-stu-id="e9ec1-122">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="e9ec1-123">Adicione um grupo de segurança contendo usuários do cartão inteligente com permissões para Ler/Registrar (Permitir), ou</span><span class="sxs-lookup"><span data-stu-id="e9ec1-123">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="e9ec1-124">Adicione o grupo do Usuário de Domínio com as permissões para Ler/Registrar (Permitir)</span><span class="sxs-lookup"><span data-stu-id="e9ec1-124">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

## <a name="configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="e9ec1-125">Configuração do Windows 8 para cartões inteligentes virtuais</span><span class="sxs-lookup"><span data-stu-id="e9ec1-125">Configure Windows 8 for Virtual Smart Cards</span></span>

<span data-ttu-id="e9ec1-126">Um fator que deve ser levado em consideração na implantação da autenticação de dois fatores e na tecnologia de cartão inteligente é o custo da implementação.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-126">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="e9ec1-127">Windows 8 fornece um número de novos recursos de segurança e um dos novos recursos mais interessantes é o suporte para cartões de inteligentes virtuais.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-127">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="e9ec1-128">Para computadores que contam com um chip Trusted Platform Module (TPM) compatível com a especificação da versão 1.2, as organizações podem agora se beneficiar do logon com cartões inteligentes sem fazer mais nenhum investimento em hardware.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-128">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="e9ec1-129">Para obter mais informações, consulte [usando Virtual cartões inteligentes com o Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).</span><span class="sxs-lookup"><span data-stu-id="e9ec1-129">For more information, see [Using Virtual Smart Cards with Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).</span></span>

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="e9ec1-130">Para configurar o Windows 8 para cartões inteligentes virtuais</span><span class="sxs-lookup"><span data-stu-id="e9ec1-130">To Configure Windows 8 for Virtual Smart Cards</span></span>

1. <span data-ttu-id="e9ec1-131">Faça logon computador Windows 8 usando as credenciais de um Skype para usuário habilitado para negócios.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-131">Log in to the Windows 8 computer using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="e9ec1-132">Na tela Iniciar do Windows 8, mova seu cursor para o canto inferior direito da tela.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-132">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3. <span data-ttu-id="e9ec1-133">Selecione a opção de **pesquisa** e pesquise forCommand Prompt.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-133">Select the **Search** option, and then search forCommand Prompt.</span></span>

4. <span data-ttu-id="e9ec1-134">Clique com o botão direito do mouse em **Prompt de comando** e selecione **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-134">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5. <span data-ttu-id="e9ec1-135">Abra o Console de Gerenciamento do Trusted Platform Module (TPM) executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e9ec1-135">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>

  ```
  Tpm.msc
  ```

6. <span data-ttu-id="e9ec1-136">No Console de Gerenciamento do TPM, confira se a versão do seu TPM é 1.2 ou superior.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-136">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>

    > [!NOTE]
    > <span data-ttu-id="e9ec1-137">Caso surja uma caixa de diálogo com a mensagem de que não foi possível encontrar o Trust Platform Module (TPM) compatível, verifique se o computador tem um módulo TPM compatível e se ele está habilitado na BIOS do sistema.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-137">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

7. <span data-ttu-id="e9ec1-138">Feche o Console de Gerenciamento do TPM</span><span class="sxs-lookup"><span data-stu-id="e9ec1-138">Close the TPM management console</span></span>

8. <span data-ttu-id="e9ec1-139">No prompt de comando, crie um novo cartão inteligente virtual usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e9ec1-139">From the command prompt, create a new virtual smart card using the following command:</span></span>

  ```
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > <span data-ttu-id="e9ec1-140">Para personalizar o valor do PIN ao criar o cartão inteligente virtual, use o prompt /pin.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-140">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

9. <span data-ttu-id="e9ec1-141">No prompt de comando, abre o Console de Gerenciamento do computador executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e9ec1-141">From the command prompt, open the Computer Management console by running the following command:</span></span>

  ```
  CompMgmt.msc
  ```

10. <span data-ttu-id="e9ec1-142">No Console de Gerenciamento do computador, selecione **Gerenciamento de Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-142">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="e9ec1-143">Expanda **Leitores de cartão inteligente**.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-143">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="e9ec1-144">Verifique se o novo leitor de cartão inteligente virtual foi criado com êxito.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-144">Verify that the new virtual smart card reader has been created successfully.</span></span>

## <a name="enroll-users-for-smart-card-authentication"></a><span data-ttu-id="e9ec1-145">Registrar usuários para a autenticação de cartão inteligente</span><span class="sxs-lookup"><span data-stu-id="e9ec1-145">Enroll users for smart card authentication</span></span>

<span data-ttu-id="e9ec1-p104">Em geral, há dois métodos para registrar usuários para autenticação de cartão inteligente. O método mais fácil envolve ter usuários registrados diretamente para autenticação de cartão inteligente usando o registro via Web, enquanto o método mais complexo envolve o uso de um agente de registro. Este tópico se concentra no autorregistro para certificados de cartões inteligentes.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-p104">There are generally two methods for enrolling users for smart card authentication. The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent. This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="e9ec1-149">Para obter mais informações sobre como registrar em nome de usuários como um agente de registro, consulte [registrar para certificados em nome de outros usuários](https://go.microsoft.com/fwlink/p/?LinkID=313367).</span><span class="sxs-lookup"><span data-stu-id="e9ec1-149">For more information on enrolling on behalf of users as an enrollment agent, see [Enroll for Certificates on Behalf of Other Users](https://go.microsoft.com/fwlink/p/?LinkID=313367).</span></span>

### <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="e9ec1-150">Para registrar usuários para autenticação de cartão inteligente</span><span class="sxs-lookup"><span data-stu-id="e9ec1-150">To Enroll Users for Smart Card Authentication</span></span>

1. <span data-ttu-id="e9ec1-151">Faça logon na estação de trabalho do Windows 8 usando as credenciais de um Skype para usuário habilitado para negócios.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-151">Log in to the Windows 8 workstation using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="e9ec1-152">Inicie o Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-152">Launch Internet Explorer.</span></span>

3. <span data-ttu-id="e9ec1-153">Navegue até a página de **Inscrição de Web de autoridade de certificado** (por exemplo, https://MyCA.contoso.com/certsrv).</span><span class="sxs-lookup"><span data-stu-id="e9ec1-153">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>

    > [!NOTE]
    > <span data-ttu-id="e9ec1-154">Caso esteja usando o Internet Explorer 10, pode ser necessário visualizar esta página em Modo de Compatibilidade.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-154">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

4. <span data-ttu-id="e9ec1-155">Na **Página Inicial**, selecione **Solicitar um certificado**.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-155">On the **Welcome** Page, select **Request a certificate**.</span></span>

5. <span data-ttu-id="e9ec1-156">Em seguida, selecione **Solicitação Avançada**.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-156">Next, select **Advanced Request**.</span></span>

6. <span data-ttu-id="e9ec1-157">Selecione **Criar e enviar uma solicitação para esta autoridade de certificação**.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-157">Select **Create and submit a request to this CA**.</span></span>

7. <span data-ttu-id="e9ec1-158">Selecione **Usuário do Cartão Inteligente** na seção **Modelo de Certificado** e preencha a solicitação de certificado avançado com os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="e9ec1-158">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>

  - <span data-ttu-id="e9ec1-159">As **Opções de Chave** confirmam as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="e9ec1-159">**Key Options** confirm he following settings:</span></span>

    - <span data-ttu-id="e9ec1-160">Selecione o botão de opção **Criar novo conjunto de chaves**</span><span class="sxs-lookup"><span data-stu-id="e9ec1-160">Select the **Create new key set** radio button</span></span>

    - <span data-ttu-id="e9ec1-161">Em **CSP**, selecione **Microsoft Base Smart Card Crypto Provider**</span><span class="sxs-lookup"><span data-stu-id="e9ec1-161">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>

    - <span data-ttu-id="e9ec1-162">Em **Uso da Chave**, selecione **Exchange** (é a única opção disponível).</span><span class="sxs-lookup"><span data-stu-id="e9ec1-162">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>

    - <span data-ttu-id="e9ec1-163">Em **Tamanho da Chave**, digite 2048</span><span class="sxs-lookup"><span data-stu-id="e9ec1-163">For **Key Size**, enter 2048</span></span>

    - <span data-ttu-id="e9ec1-164">Confirme se a opção **Nome de contêiner de chave automático** está selecionada</span><span class="sxs-lookup"><span data-stu-id="e9ec1-164">Confirm that **Automatic key container name** is selected</span></span>

    - <span data-ttu-id="e9ec1-165">Deixe as outras caixas desmarcadas.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-165">Leave the other boxes unchecked.</span></span>

  - <span data-ttu-id="e9ec1-166">Em **Opções Adicionais**, confirme os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="e9ec1-166">Under **Additional Options** confirm the following values:</span></span>

    - <span data-ttu-id="e9ec1-167">Em **Formato da Solicitação**, selecione **CMC**.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-167">For **Request Format** select **CMC**.</span></span>

    - <span data-ttu-id="e9ec1-168">Em **Algoritmo de Hash**, selecione **sha1**.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-168">For **Hash Algorithm** select **sha1**.</span></span>

    - <span data-ttu-id="e9ec1-169">Para o **Nome amigável** enterSmardcard certificado.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-169">For **Friendly Name** enterSmardcard Certificate.</span></span>

8. <span data-ttu-id="e9ec1-170">Caso você esteja usando um leitor de cartão inteligente físico, insira o cartão inteligente no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-170">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9. <span data-ttu-id="e9ec1-171">Clique em **Enviar** para enviar a solicitação do certificado.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-171">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="e9ec1-172">Quando solicitado, digite o PIN usado para criar o cartão inteligente virtual.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-172">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e9ec1-173">O valor PIN do cartão de inteligente virtual padrão é '12345678'.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-173">The default virtual smart card PIN value is '12345678'.</span></span>

11. <span data-ttu-id="e9ec1-174">Depois que o certificado tiver sido emitido, clique em **Instalar este certificado** para concluir o processo de registro.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-174">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="e9ec1-175">Se sua solicitação de certificado falhar com o erro "este navegador da Web não oferece suporte a geração de solicitações de certificado", há três maneiras possíveis para resolver o problema:</span><span class="sxs-lookup"><span data-stu-id="e9ec1-175">If your certificate request fails with the error "This Web browser does not support the generation of certificate requests," there are three possible ways to resolve the issue:</span></span>

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a><span data-ttu-id="e9ec1-176">Configuração dos Serviços de Federação do Active Directory (AD FS 2.0)</span><span class="sxs-lookup"><span data-stu-id="e9ec1-176">Configure Active Directory Federation Services (AD FS 2.0)</span></span>

<span data-ttu-id="e9ec1-177">A seção a seguir descreve como configurar o Serviços de Federação do Active Directory (AD FS 2.0) para dar suporte à autenticação multifator.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-177">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="e9ec1-178">Para obter informações sobre como instalar o AD FS 2.0, consulte [AD FS 2.0 Step e guias como para](https://go.microsoft.com/fwlink/p/?LinkId=313374).</span><span class="sxs-lookup"><span data-stu-id="e9ec1-178">For information on how to install AD FS 2.0, see [AD FS 2.0 Step-by-Step and How To Guides](https://go.microsoft.com/fwlink/p/?LinkId=313374).</span></span>

> [!NOTE]
> <span data-ttu-id="e9ec1-179">Ao instalar o AD FS 2.0, não use o Windows Server Manager para adicionar a função do Active Directory Federation.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-179">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="e9ec1-180">Em vez disso, baixe e instale o [pacote do Active Directory Federation Services 2.0 RTW](https://go.microsoft.com/fwlink/p/?LinkId=313375).</span><span class="sxs-lookup"><span data-stu-id="e9ec1-180">Instead, download and install the [Active Directory Federation Services 2.0 RTW package](https://go.microsoft.com/fwlink/p/?LinkId=313375).</span></span>

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a><span data-ttu-id="e9ec1-181">Para configurar o AD FS para autenticação de dois fatores</span><span class="sxs-lookup"><span data-stu-id="e9ec1-181">To configure AD FS for two-factor Authentication</span></span>

1. <span data-ttu-id="e9ec1-182">Faça logon no computador do AD FS 2.0 utilizando uma conta de Administrador de Domínio.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-182">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="e9ec1-183">Inicie o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-183">Start Windows PowerShell.</span></span>

3. <span data-ttu-id="e9ec1-184">Na linha de comando do Windows PowerShell, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e9ec1-184">From the Windows PowerShell command-line, run the following command:</span></span>

  ```
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. <span data-ttu-id="e9ec1-185">Estabeleça uma parceria com cada servidor que será habilitado para a autenticação passiva executando o seguinte comando, substituindo pelo nome do servidor específico de sua implantação:</span><span class="sxs-lookup"><span data-stu-id="e9ec1-185">Establish a partnership with each server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>

  ```
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. <span data-ttu-id="e9ec1-186">No menu Ferramentas Administrativas, inicie o Console de Gerenciamento do AD FS 2.0.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-186">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6. <span data-ttu-id="e9ec1-187">Expanda **relações de confiança** > **confiança de terceira parte confiável**.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-187">Expand **Trust Relationships** > **Relying Party Trusts**.</span></span>

7. <span data-ttu-id="e9ec1-188">Verificar se uma nova relação de confiança foi criada para sua Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-188">Verify that a new trust has been created for your Skype for Business Server.</span></span>

8. <span data-ttu-id="e9ec1-189">Crie e atribua uma Regra de Autorização de Emissão para seu objeto de confiança de terceira parte confiável usando o Windows PowerShell executando os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="e9ec1-189">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. <span data-ttu-id="e9ec1-190">Crie e atribua uma Regra de Transformação de Emissão para seu objeto de confiança de terceira parte confiável usando o Windows PowerShell executando os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="e9ec1-190">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. <span data-ttu-id="e9ec1-191">No Console de Gerenciamento do AD FS 2.0, clique com o botão direito no seu objeto de confiança de terceira parte confiável e selecione **Editar Regras de Declaração**.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-191">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="e9ec1-192">Selecione a guia **Regras de Autorização de Emissão** e verifique se a nova regra de autorização foi criada com sucesso.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-192">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="e9ec1-193">Selecione a guia **Regras de Transformação de Emissão** e verifique se a nova regra de transformação foi criada com sucesso.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-193">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="e9ec1-194">Configuração do AD FS 2.0 para suporte à autenticação de cliente</span><span class="sxs-lookup"><span data-stu-id="e9ec1-194">Configuring AD FS 2.0 to support client authentication</span></span>

<span data-ttu-id="e9ec1-195">Há dois tipos possíveis de autenticação que podem ser configurados para permitir que o AD FS 2.0 suporte autenticações utilizando cartões inteligentes:</span><span class="sxs-lookup"><span data-stu-id="e9ec1-195">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

- <span data-ttu-id="e9ec1-196">Autenticação baseada em formulário (FBA)</span><span class="sxs-lookup"><span data-stu-id="e9ec1-196">Forms-based authentication (FBA)</span></span>

- <span data-ttu-id="e9ec1-197">Autenticação de Cliente de Segurança na Camada de Transporte</span><span class="sxs-lookup"><span data-stu-id="e9ec1-197">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="e9ec1-198">Utilizando a autenticação baseada em formulários, você pode desenvolver uma página da Web que permite que os usuários autentiquem usando seus nomes de usuário/senhas ou usando o cartão inteligente e o PIN.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-198">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="e9ec1-199">Este tópico tem como foco como implementar a Autenticação de Cliente de Segurança na Camada de Transporte com o AD FS 2.0.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-199">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="e9ec1-200">Para obter mais informações sobre os tipos de autenticação 2.0 do AD FS, consulte [AD FS 2.0: como alterar o tipo de autenticação Local](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span><span class="sxs-lookup"><span data-stu-id="e9ec1-200">For more information about AD FS 2.0 authentication types, see [AD FS 2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span></span>

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="e9ec1-201">Para configurar o AD FS 2.0 para suportar a autenticação de cliente</span><span class="sxs-lookup"><span data-stu-id="e9ec1-201">To Configure AD FS 2.0 to Support Client Authentication</span></span>

1. <span data-ttu-id="e9ec1-202">Faça logon no computador do AD FS 2.0 utilizando uma conta de Administrador de Domínio.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-202">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="e9ec1-203">Inicie o Windows Explorer.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-203">Launch Windows Explorer.</span></span>

3. <span data-ttu-id="e9ec1-204">Navegue até C:\inetpub\adfs\ls</span><span class="sxs-lookup"><span data-stu-id="e9ec1-204">Browse to C:\inetpub\adfs\ls</span></span>

4. <span data-ttu-id="e9ec1-205">Faça uma cópia de backup do arquivo web.config existente.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-205">Make a backup copy of the existing web.config file.</span></span>

5. <span data-ttu-id="e9ec1-206">Abra o arquivo web.config existente utilizando o Bloco de Notas.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-206">Open the existing web.config file using Notepad.</span></span>

6. <span data-ttu-id="e9ec1-207">Na barra de Menu, selecione **Editar** e, em seguida, selecione **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-207">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7. <span data-ttu-id="e9ec1-208">Procurar \<localAuthenticationTypes\>.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-208">Search for \<localAuthenticationTypes\>.</span></span>

    <span data-ttu-id="e9ec1-209">Observe que há quatro tipos de autenticação listados, um por linha.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-209">Note that there are four authentication types listed, one per line.</span></span>

8. <span data-ttu-id="e9ec1-210">Mova para a linha que contém o tipo de autenticação TLSClient para o topo da lista na seção.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-210">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9. <span data-ttu-id="e9ec1-211">Salve e Feche o arquivo web.config.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-211">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="e9ec1-212">Inicie um Prompt de Comando com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-212">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="e9ec1-213">Reinicie o IIS executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e9ec1-213">Restart IIS by running the following command:</span></span>

  ```
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a><span data-ttu-id="e9ec1-214">Configuração da autenticação passiva do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e9ec1-214">Configuring Skype for Business Server passive authentication</span></span>

<span data-ttu-id="e9ec1-215">A seção a seguir descreve como configurar Skype para Business Server oferecer suporte à autenticação passiva.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-215">The following section describes how to configure Skype for Business Server to support passive authentication.</span></span> <span data-ttu-id="e9ec1-216">Quando habilitado, os usuários habilitados para autenticação de dois fatores será necessários usar um cartão inteligente de físico ou virtual e um PIN válido para entrar usando o Skype para o cliente de negócios.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-216">Once enabled, users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Skype for Business client.</span></span>

> [!NOTE]
> <span data-ttu-id="e9ec1-p109">Recomendamos que os clientes habilitem a autenticação passiva para o Registrador e para os Serviços Web no nível de serviço. Caso a autenticação passiva esteja habilitada para o Registrador e para os Serviços Web no nível global, é provável que ocorram falhas de autenticação em toda a organização para usuários que não estão se conectando com o cliente de desktop compatível.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-p109">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level. If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the supported desktop client.</span></span>

### <a name="web-service-configuration"></a><span data-ttu-id="e9ec1-219">Configuração dos Serviços Web</span><span class="sxs-lookup"><span data-stu-id="e9ec1-219">Web Service Configuration</span></span>

<span data-ttu-id="e9ec1-220">As etapas a seguir descrevem como criar uma configuração personalizada de serviços Web para servidores Diretores, pools Enterprise e Standard Edition que serão habilitados para a autenticação passiva.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-220">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-web-service-configuration"></a><span data-ttu-id="e9ec1-221">Para criar uma configuração personalizada de serviços Web</span><span class="sxs-lookup"><span data-stu-id="e9ec1-221">To create a custom web service configuration</span></span>

1. <span data-ttu-id="e9ec1-222">Faça logon em seu Skype para servidor de Front End do servidor de negócios usando um Skype para a conta de administrador de negócios.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-222">Log in to your Skype for Business Server Front End server using a Skype for Business administrator account.</span></span>

2. <span data-ttu-id="e9ec1-223">Inicie o Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-223">Launch the Skype for Business Server Management Shell.</span></span>

3. <span data-ttu-id="e9ec1-224">No Skype para Business Server Management Shell de linha de comando, crie uma nova configuração do serviço Web para cada diretor, Pool Enterprise e servidor Standard Edition que será habilitado para autenticação passiva executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e9ec1-224">From the Skype for Business Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>

  ```
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > <span data-ttu-id="e9ec1-p110">O valor para o FQDN WsFedPassiveMetadataUri é o Nome de Serviço de Federação do seu servidor AD FS 2.0. O valor do Nome de Serviço de Federação pode ser encontrado no Console de Gerenciamento do AD FS 2.0 clicando com o botão direito do mouse em **Serviço** a partir do painel de navegação, selecionando em seguida **Editar propriedades do serviço de federação**.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-p110">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server. The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on **Service** from the navigation pane and then selecting **Edit Federation Service Properties**.</span></span>

4. <span data-ttu-id="e9ec1-227">Verifique se os valores UseWsFedPassiveAuth e WsFedPassiveMetadataUri foram definidos corretamente executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e9ec1-227">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>

  ```
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. <span data-ttu-id="e9ec1-228">Para clientes, a Autenticação Passiva é o método de autenticação menos indicado para autenticação de webticket.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-228">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="e9ec1-229">Para todos os diretores, Pools Enterprise e servidores Standard Edition que serão habilitados para autenticação passiva, todos os outros tipos de autenticação devem ser desabilitados no Skype para serviços corporativos de Web executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e9ec1-229">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Skype for Business Web Services by running the following cmdlet:</span></span>

  ```
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. <span data-ttu-id="e9ec1-230">Verifique se todos os outros tipos de autenticação foram desabilitados com sucesso executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e9ec1-230">Verify that all other authentication types have been successfully disabled by running the following cmdlet:</span></span>

  ```
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a><span data-ttu-id="e9ec1-231">Configuração de proxy</span><span class="sxs-lookup"><span data-stu-id="e9ec1-231">Proxy Configuration</span></span>

<span data-ttu-id="e9ec1-232">Quando a autenticação de certificado estiver desabilitada para Skype para serviços da Web de negócios, o Skype para o cliente de negócios usará um tipo de autenticação menos preferencial, como Kerberos ou NTLM, para autenticar ao serviço registrador.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-232">When certificate authentication is disabled for Skype for Business Web Services, the Skype for Business client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="e9ec1-233">Autenticação de certificado ainda é necessários para permitir que o cliente recuperar um webticket, no entanto, o Kerberos e NTLM devem ser desabilitados para o serviço registrador.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-233">Certificate authentication is still needed to allow the client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="e9ec1-234">As etapas a seguir descrevem como criar uma configuração personalizada de proxy para servidores de pools Edge, pools Enterprise e Standard Edition que serão habilitados para a autenticação passiva.</span><span class="sxs-lookup"><span data-stu-id="e9ec1-234">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-proxy-configuration"></a><span data-ttu-id="e9ec1-235">Para criar uma configuração personalizada de proxy</span><span class="sxs-lookup"><span data-stu-id="e9ec1-235">To create a custom proxy configuration</span></span>

1. <span data-ttu-id="e9ec1-236">No Skype para Business Server Management Shell de linha de comando, crie uma nova configuração de proxy para cada Skype para o Pool de borda do servidor de negócios, Pool Enterprise e Standard Edition server que será habilitado para autenticação passiva executando o seguinte comandos:</span><span class="sxs-lookup"><span data-stu-id="e9ec1-236">From the Skype for Business Server Management Shell command-line, create a new proxy configuration for each Skype for Business Server Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>

  ```
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. <span data-ttu-id="e9ec1-237">Verifique se todos os outros tipos de autenticação de proxy foram desabilitados com sucesso executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e9ec1-237">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>

  ```
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a><span data-ttu-id="e9ec1-238">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e9ec1-238">See also</span></span>

[<span data-ttu-id="e9ec1-239">Gerenciar a autenticação de dois fatores no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="e9ec1-239">Manage two-factor authentication in Skype for Business Server</span></span>](two-factor-authentication.md)

[<span data-ttu-id="e9ec1-240">Usar a autenticação de dois fatores com Skype para o cliente de negócios e Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="e9ec1-240">Use two-factor authentication with Skype for Business client and Skype for Business Server</span></span>](use.md)