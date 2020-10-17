---
title: 'Lync Server 2013: Configurando o AD FS 2,0 para dar suporte à autenticação de cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring AD FS 2.0 to support client authentication
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308565(v=OCS.15)
ms:contentKeyID: 54973687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d2b713d109a72431e78e966258a84c084523a7a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517638"
---
# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a><span data-ttu-id="98276-102">Configurando o AD FS 2,0 para suportar a autenticação de cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98276-102">Configuring AD FS 2.0 to support client authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98276-103">_**Última modificação do tópico:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="98276-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="98276-104">Há dois tipos de autenticação possíveis que podem ser configurados para permitir que o AD FS 2,0 suporte a autenticação usando cartões inteligentes:</span><span class="sxs-lookup"><span data-stu-id="98276-104">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

  - <span data-ttu-id="98276-105">Autenticação baseada em formulários (FBA)</span><span class="sxs-lookup"><span data-stu-id="98276-105">Forms-based authentication (FBA)</span></span>

  - <span data-ttu-id="98276-106">Autenticação do cliente de segurança da camada de transporte</span><span class="sxs-lookup"><span data-stu-id="98276-106">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="98276-107">Usando a autenticação baseada em formulários, você pode desenvolver uma página da Web que permita que os usuários sejam autenticados usando seu nome de usuário/senha ou usando o cartão inteligente e o PIN.</span><span class="sxs-lookup"><span data-stu-id="98276-107">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="98276-108">Este tópico se concentra em como implementar a autenticação de cliente de segurança de camada de transporte com o AD FS 2,0.</span><span class="sxs-lookup"><span data-stu-id="98276-108">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="98276-109">Para obter mais informações sobre os tipos de autenticação do AD FS 2,0, consulte AD FS 2,0: como alterar o tipo de autenticação local em [https://go.microsoft.com/fwlink/p/?LinkId=313384](https://go.microsoft.com/fwlink/p/?linkid=313384) .</span><span class="sxs-lookup"><span data-stu-id="98276-109">For more information about AD FS 2.0 authentication types, see AD FS 2.0: How to Change the Local Authentication Type at [https://go.microsoft.com/fwlink/p/?LinkId=313384](https://go.microsoft.com/fwlink/p/?linkid=313384).</span></span>

<div>


<span data-ttu-id="98276-110">**Para configurar o AD FS 2,0 para suportar a autenticação de cliente**</span><span class="sxs-lookup"><span data-stu-id="98276-110">**To Configure AD FS 2.0 to Support Client Authentication**</span></span>

1.  <span data-ttu-id="98276-111">Faça logon no computador do AD FS 2,0 usando uma conta de administrador de domínio.</span><span class="sxs-lookup"><span data-stu-id="98276-111">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="98276-112">Inicie o Windows Explorer.</span><span class="sxs-lookup"><span data-stu-id="98276-112">Launch Windows Explorer.</span></span>

3.  <span data-ttu-id="98276-113">Navegue até C: \\ Inetpub \\ ADFS \\ ls</span><span class="sxs-lookup"><span data-stu-id="98276-113">Browse to C:\\inetpub\\adfs\\ls</span></span>

4.  <span data-ttu-id="98276-114">Faça uma cópia de backup do arquivo de web.config existente.</span><span class="sxs-lookup"><span data-stu-id="98276-114">Make a backup copy of the existing web.config file.</span></span>

5.  <span data-ttu-id="98276-115">Abra o arquivo de web.config existente usando o bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="98276-115">Open the existing web.config file using Notepad.</span></span>

6.  <span data-ttu-id="98276-116">Na barra de menus, selecione **Editar** e, em seguida, selecione **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="98276-116">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7.  <span data-ttu-id="98276-117">Pesquisa **\<localAuthenticationTypes\>** .</span><span class="sxs-lookup"><span data-stu-id="98276-117">Search for **\<localAuthenticationTypes\>**.</span></span>
    
    <span data-ttu-id="98276-118">Observe que há quatro tipos de autenticação listados, um por linha.</span><span class="sxs-lookup"><span data-stu-id="98276-118">Note that there are four authentication types listed, one per line.</span></span>

8.  <span data-ttu-id="98276-119">Mova a linha que contém o tipo de autenticação TLSClient para a parte superior da lista na seção.</span><span class="sxs-lookup"><span data-stu-id="98276-119">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9.  <span data-ttu-id="98276-120">Salve e feche o arquivo web.config.</span><span class="sxs-lookup"><span data-stu-id="98276-120">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="98276-121">Inicie um prompt de comando com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="98276-121">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="98276-122">Reinicie o IIS executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="98276-122">Restart IIS by running the following command:</span></span>
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

