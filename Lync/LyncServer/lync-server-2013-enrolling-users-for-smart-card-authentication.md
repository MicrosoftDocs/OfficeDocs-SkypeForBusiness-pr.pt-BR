---
title: 'Lync Server 2013: registrar usuários para autenticação de cartão inteligente'
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
ms.openlocfilehash: cfbfcd73aba4079d74074adcd2710b8a2d45aeba
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526768"
---
# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="860b2-102">Registrar usuários para autenticação de cartão inteligente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="860b2-102">Enrolling users for smart card authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="860b2-103">_**Última modificação do tópico:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="860b2-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="860b2-104">Em geral, há dois métodos para registrar usuários para autenticação de cartão inteligente.</span><span class="sxs-lookup"><span data-stu-id="860b2-104">There are generally two methods for enrolling users for smart card authentication.</span></span> <span data-ttu-id="860b2-105">O método mais fácil envolve ter os usuários se inscrever diretamente para a autenticação de cartão inteligente usando o registro na Web, enquanto o método mais complexo envolve o uso de um agente de registro.</span><span class="sxs-lookup"><span data-stu-id="860b2-105">The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent.</span></span> <span data-ttu-id="860b2-106">Este tópico se concentra no Autoregistro de certificados de cartão inteligente.</span><span class="sxs-lookup"><span data-stu-id="860b2-106">This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="860b2-107">Para obter mais informações sobre o registro em nome de usuários como um agente de registro, consulte registrar-se para certificados em nome de outros usuários em [https://go.microsoft.com/fwlink/p/?LinkID=313367](https://go.microsoft.com/fwlink/p/?linkid=313367) .</span><span class="sxs-lookup"><span data-stu-id="860b2-107">For more information on enrolling on behalf of users as an enrollment agent, see Enroll for Certificates on Behalf of Other Users at [https://go.microsoft.com/fwlink/p/?LinkID=313367](https://go.microsoft.com/fwlink/p/?linkid=313367).</span></span>

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="860b2-108">Para registrar usuários para autenticação de cartão inteligente</span><span class="sxs-lookup"><span data-stu-id="860b2-108">To Enroll Users for Smart Card Authentication</span></span>

1.  <span data-ttu-id="860b2-109">Faça logon na estação de trabalho do Windows 8 usando as credenciais de um usuário habilitado para Lync.</span><span class="sxs-lookup"><span data-stu-id="860b2-109">Log in to the Windows 8 workstation using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="860b2-110">Inicie o Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="860b2-110">Launch Internet Explorer.</span></span>

3.  <span data-ttu-id="860b2-111">Navegue até a página **registro da Web da autoridade de certificação** (por exemplo, https://MyCA.contoso.com/certsrv) .</span><span class="sxs-lookup"><span data-stu-id="860b2-111">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="860b2-112">Se você estiver usando o Internet Explorer 10, talvez seja necessário exibir este site no modo de compatibilidade.</span><span class="sxs-lookup"><span data-stu-id="860b2-112">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

4.  <span data-ttu-id="860b2-113">Na página de **boas-vindas** , selecione **solicitar um certificado**.</span><span class="sxs-lookup"><span data-stu-id="860b2-113">On the **Welcome** Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="860b2-114">Em seguida, selecione **solicitação avançada**.</span><span class="sxs-lookup"><span data-stu-id="860b2-114">Next, select **Advanced Request**.</span></span>

6.  <span data-ttu-id="860b2-115">Selecione **criar e enviar uma solicitação para esta autoridade de certificação**.</span><span class="sxs-lookup"><span data-stu-id="860b2-115">Select **Create and submit a request to this CA**.</span></span>

7.  <span data-ttu-id="860b2-116">Selecione **usuário de cartão inteligente** na seção **modelo de certificado** e conclua a solicitação avançada de certificado com os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="860b2-116">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>
    
      - <span data-ttu-id="860b2-117">As **principais opções** confirmam as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="860b2-117">**Key Options** confirm he following settings:</span></span>
        
          - <span data-ttu-id="860b2-118">Selecione o botão de opção **criar novo conjunto de chaves**</span><span class="sxs-lookup"><span data-stu-id="860b2-118">Select the **Create new key set** radio button</span></span>
        
          - <span data-ttu-id="860b2-119">Para o **CSP**, selecione **Microsoft base cartão inteligente Crypto Provider**</span><span class="sxs-lookup"><span data-stu-id="860b2-119">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>
        
          - <span data-ttu-id="860b2-120">Para **uso de chave**, selecione **Exchange** (essa é a única opção disponível).</span><span class="sxs-lookup"><span data-stu-id="860b2-120">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>
        
          - <span data-ttu-id="860b2-121">Em **tamanho da chave**, digite **2048**</span><span class="sxs-lookup"><span data-stu-id="860b2-121">For **Key Size**, enter **2048**</span></span>
        
          - <span data-ttu-id="860b2-122">Confirmar se o **nome do contêiner de chave automático** está selecionado</span><span class="sxs-lookup"><span data-stu-id="860b2-122">Confirm that **Automatic key container name** is selected</span></span>
        
          - <span data-ttu-id="860b2-123">Deixe as outras caixas desmarcadas.</span><span class="sxs-lookup"><span data-stu-id="860b2-123">Leave the other boxes unchecked.</span></span>
    
      - <span data-ttu-id="860b2-124">Em **Opções adicionais** , confirme os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="860b2-124">Under **Additional Options** confirm the following values:</span></span>
        
          - <span data-ttu-id="860b2-125">Para o **formato de solicitação** , selecione **CMC**.</span><span class="sxs-lookup"><span data-stu-id="860b2-125">For **Request Format** select **CMC**.</span></span>
        
          - <span data-ttu-id="860b2-126">Para **algoritmo de hash** , selecione **SHA1**.</span><span class="sxs-lookup"><span data-stu-id="860b2-126">For **Hash Algorithm** select **sha1**.</span></span>
        
          - <span data-ttu-id="860b2-127">Para **nome amigável** , insira o **certificado Smardcard**.</span><span class="sxs-lookup"><span data-stu-id="860b2-127">For **Friendly Name** enter **Smardcard Certificate**.</span></span>

8.  <span data-ttu-id="860b2-128">Se você estiver usando um leitor de SmartCard físico, insira o cartão inteligente no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="860b2-128">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9.  <span data-ttu-id="860b2-129">Clique em **Enviar** para enviar a solicitação de certificado.</span><span class="sxs-lookup"><span data-stu-id="860b2-129">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="860b2-130">Quando solicitado, insira o PIN usado para criar o cartão inteligente virtual.</span><span class="sxs-lookup"><span data-stu-id="860b2-130">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="860b2-131">O valor padrão de PIN do cartão inteligente virtual é ' 12345678 '.</span><span class="sxs-lookup"><span data-stu-id="860b2-131">The default virtual smart card PIN value is ‘12345678’.</span></span>

    
    </div>

11. <span data-ttu-id="860b2-132">Depois que o certificado for emitido, clique em **instalar este certificado** para concluir o processo de registro.</span><span class="sxs-lookup"><span data-stu-id="860b2-132">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="860b2-133">Se a solicitação de certificado falhar com o erro "Este navegador da Web não dá suporte à geração de solicitações de certificado", há três maneiras possíveis de resolver o problema:</span><span class="sxs-lookup"><span data-stu-id="860b2-133">If your certificate request fails with the error “This Web browser does not support the generation of certificate requests,” there are three possible ways to resolve the issue:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="860b2-134">Habilitar o modo de exibição de compatibilidade no Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="860b2-134">Enable Compatibility View in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="860b2-135">Habilitar a opção Ativar configurações da intranet no Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="860b2-135">Enable the Turn on Intranet settings option in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="860b2-136">Selecione a configuração redefinir todas as zonas para o nível padrão na guia Segurança no menu opções do Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="860b2-136">Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.</span></span></P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

