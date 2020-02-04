---
title: 'Lync Server 2013: registrando usuários para autenticação de cartão inteligente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enrolling users for smart card authentication
ms:assetid: a6445a83-a94b-423f-ba2a-12b5f84c5d75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308570(v=OCS.15)
ms:contentKeyID: 54973691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 750e77b342b48d2c81bf05e160779ca5566f5a2f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="d0363-102">Registrar usuários para autenticação de cartão inteligente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0363-102">Enrolling users for smart card authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0363-103">_**Tópico da última modificação:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="d0363-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="d0363-p101">Em geral, há dois métodos para registrar usuários para autenticação de cartão inteligente. O método mais fácil envolve ter usuários registrados diretamente para autenticação de cartão inteligente usando o registro via Web, enquanto o método mais complexo envolve o uso de um agente de registro. Este tópico se concentra no autorregistro para certificados de cartões inteligentes.</span><span class="sxs-lookup"><span data-stu-id="d0363-p101">There are generally two methods for enrolling users for smart card authentication. The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent. This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="d0363-107">Para obter mais informações sobre como registrar-se em nome dos usuários como um agente de inscrição, consulte registrar-se para obter certificados [http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367)em nome de outros usuários em.</span><span class="sxs-lookup"><span data-stu-id="d0363-107">For more information on enrolling on behalf of users as an enrollment agent, see Enroll for Certificates on Behalf of Other Users at [http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367).</span></span>

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="d0363-108">Para registrar usuários para autenticação de cartão inteligente</span><span class="sxs-lookup"><span data-stu-id="d0363-108">To Enroll Users for Smart Card Authentication</span></span>

1.  <span data-ttu-id="d0363-109">Faça logon na estação de trabalho do Windows 8 usando as credenciais de um usuário compatível com o Lync.</span><span class="sxs-lookup"><span data-stu-id="d0363-109">Log in to the Windows 8 workstation using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="d0363-110">Inicie o Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="d0363-110">Launch Internet Explorer.</span></span>

3.  <span data-ttu-id="d0363-111">Navegue até a página de **registro na Web da autoridade** de https://MyCA.contoso.com/certsrv)certificação (por exemplo,.</span><span class="sxs-lookup"><span data-stu-id="d0363-111">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d0363-112">Caso esteja usando o Internet Explorer 10, pode ser necessário visualizar esta página em Modo de Compatibilidade.</span><span class="sxs-lookup"><span data-stu-id="d0363-112">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

4.  <span data-ttu-id="d0363-113">Na **Página Inicial**, selecione **Solicitar um certificado**.</span><span class="sxs-lookup"><span data-stu-id="d0363-113">On the **Welcome** Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="d0363-114">Em seguida, selecione **Solicitação Avançada**.</span><span class="sxs-lookup"><span data-stu-id="d0363-114">Next, select **Advanced Request**.</span></span>

6.  <span data-ttu-id="d0363-115">Selecione **Criar e enviar uma solicitação para esta autoridade de certificação**.</span><span class="sxs-lookup"><span data-stu-id="d0363-115">Select **Create and submit a request to this CA**.</span></span>

7.  <span data-ttu-id="d0363-116">Selecione **Usuário do Cartão Inteligente** na seção **Modelo de Certificado** e preencha a solicitação de certificado avançado com os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="d0363-116">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>
    
      - <span data-ttu-id="d0363-117">As **Opções de Chave** confirmam as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="d0363-117">**Key Options** confirm he following settings:</span></span>
        
          - <span data-ttu-id="d0363-118">Selecione o botão de opção **Criar novo conjunto de chaves**</span><span class="sxs-lookup"><span data-stu-id="d0363-118">Select the **Create new key set** radio button</span></span>
        
          - <span data-ttu-id="d0363-119">Em **CSP**, selecione **Microsoft Base Smart Card Crypto Provider**</span><span class="sxs-lookup"><span data-stu-id="d0363-119">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>
        
          - <span data-ttu-id="d0363-120">Em **Uso da Chave**, selecione **Exchange** (é a única opção disponível).</span><span class="sxs-lookup"><span data-stu-id="d0363-120">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>
        
          - <span data-ttu-id="d0363-121">Em **Tamanho da Chave**, digite **2048**</span><span class="sxs-lookup"><span data-stu-id="d0363-121">For **Key Size**, enter **2048**</span></span>
        
          - <span data-ttu-id="d0363-122">Confirme se a opção **Nome de contêiner de chave automático** está selecionada</span><span class="sxs-lookup"><span data-stu-id="d0363-122">Confirm that **Automatic key container name** is selected</span></span>
        
          - <span data-ttu-id="d0363-123">Deixe as outras caixas desmarcadas.</span><span class="sxs-lookup"><span data-stu-id="d0363-123">Leave the other boxes unchecked.</span></span>
    
      - <span data-ttu-id="d0363-124">Em **Opções Adicionais**, confirme os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="d0363-124">Under **Additional Options** confirm the following values:</span></span>
        
          - <span data-ttu-id="d0363-125">Em **Formato da Solicitação**, selecione **CMC**.</span><span class="sxs-lookup"><span data-stu-id="d0363-125">For **Request Format** select **CMC**.</span></span>
        
          - <span data-ttu-id="d0363-126">Em **Algoritmo de Hash**, selecione **sha1**.</span><span class="sxs-lookup"><span data-stu-id="d0363-126">For **Hash Algorithm** select **sha1**.</span></span>
        
          - <span data-ttu-id="d0363-127">Em **Nome Amigável**, digite **Smardcard Certificate**.</span><span class="sxs-lookup"><span data-stu-id="d0363-127">For **Friendly Name** enter **Smardcard Certificate**.</span></span>

8.  <span data-ttu-id="d0363-128">Caso você esteja usando um leitor de cartão inteligente físico, insira o cartão inteligente no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d0363-128">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9.  <span data-ttu-id="d0363-129">Clique em **Enviar** para enviar a solicitação do certificado.</span><span class="sxs-lookup"><span data-stu-id="d0363-129">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="d0363-130">Quando solicitado, digite o PIN usado para criar o cartão inteligente virtual.</span><span class="sxs-lookup"><span data-stu-id="d0363-130">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d0363-131">O PIN padrão do cartão inteligente virtual é ‘12345678’.</span><span class="sxs-lookup"><span data-stu-id="d0363-131">The default virtual smart card PIN value is ‘12345678’.</span></span>

    
    </div>

11. <span data-ttu-id="d0363-132">Depois que o certificado tiver sido emitido, clique em **Instalar este certificado** para concluir o processo de registro.</span><span class="sxs-lookup"><span data-stu-id="d0363-132">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d0363-133">Caso sua solicitação de certificado falhe com o erro “Este navegador da Web não dá suporte à geração de solicitações de certificados”, há três maneiras possíveis para resolver o problema:</span><span class="sxs-lookup"><span data-stu-id="d0363-133">If your certificate request fails with the error “This Web browser does not support the generation of certificate requests,” there are three possible ways to resolve the issue:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="d0363-134">Habilitar o Modo de Exibição de Compatibilidade no Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="d0363-134">Enable Compatibility View in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="d0363-135">Habilitar a opção Ativar configurações de Intranet no Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="d0363-135">Enable the Turn on Intranet settings option in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="d0363-136">Selecionar a configuração Restaurar o nível padrão de todas as zonas na guia Segurança no menu de opções do Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="d0363-136">Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.</span></span></P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

