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
ms.openlocfilehash: f7054bae609b5d1a1c6fe176c1092614f5d30fa6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029702"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a><span data-ttu-id="854de-102">Configurando o AD FS 2,0 para suportar a autenticação de cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="854de-102">Configuring AD FS 2.0 to support client authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="854de-103">_**Última modificação do tópico:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="854de-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="854de-104">Há dois tipos de autenticação possíveis que podem ser configurados para permitir que o AD FS 2,0 suporte a autenticação usando cartões inteligentes:</span><span class="sxs-lookup"><span data-stu-id="854de-104">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

  - <span data-ttu-id="854de-105">Autenticação baseada em formulários (FBA)</span><span class="sxs-lookup"><span data-stu-id="854de-105">Forms-based authentication (FBA)</span></span>

  - <span data-ttu-id="854de-106">Autenticação do cliente de segurança da camada de transporte</span><span class="sxs-lookup"><span data-stu-id="854de-106">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="854de-107">Usando a autenticação baseada em formulários, você pode desenvolver uma página da Web que permita que os usuários sejam autenticados usando seu nome de usuário/senha ou usando o cartão inteligente e o PIN.</span><span class="sxs-lookup"><span data-stu-id="854de-107">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="854de-108">Este tópico se concentra em como implementar a autenticação de cliente de segurança de camada de transporte com o AD FS 2,0.</span><span class="sxs-lookup"><span data-stu-id="854de-108">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="854de-109">Para obter mais informações sobre os tipos de autenticação do AD FS 2,0, consulte AD FS 2,0: como alterar o tipo [http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384)de autenticação local em.</span><span class="sxs-lookup"><span data-stu-id="854de-109">For more information about AD FS 2.0 authentication types, see AD FS 2.0: How to Change the Local Authentication Type at [http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384).</span></span>

<div>


<span data-ttu-id="854de-110">**Para configurar o AD FS 2,0 para suportar a autenticação de cliente**</span><span class="sxs-lookup"><span data-stu-id="854de-110">**To Configure AD FS 2.0 to Support Client Authentication**</span></span>

1.  <span data-ttu-id="854de-111">Faça logon no computador do AD FS 2,0 usando uma conta de administrador de domínio.</span><span class="sxs-lookup"><span data-stu-id="854de-111">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="854de-112">Inicie o Windows Explorer.</span><span class="sxs-lookup"><span data-stu-id="854de-112">Launch Windows Explorer.</span></span>

3.  <span data-ttu-id="854de-113">Navegue até C:\\Inetpub\\ADFS\\ls</span><span class="sxs-lookup"><span data-stu-id="854de-113">Browse to C:\\inetpub\\adfs\\ls</span></span>

4.  <span data-ttu-id="854de-114">Faça uma cópia de backup do arquivo Web. config existente.</span><span class="sxs-lookup"><span data-stu-id="854de-114">Make a backup copy of the existing web.config file.</span></span>

5.  <span data-ttu-id="854de-115">Abra o arquivo Web. config existente usando o bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="854de-115">Open the existing web.config file using Notepad.</span></span>

6.  <span data-ttu-id="854de-116">Na barra de menus, selecione **Editar** e, em seguida, selecione **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="854de-116">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7.  <span data-ttu-id="854de-117">Procure \*\* \<localAuthenticationTypes\>\*\*.</span><span class="sxs-lookup"><span data-stu-id="854de-117">Search for **\<localAuthenticationTypes\>**.</span></span>
    
    <span data-ttu-id="854de-118">Observe que há quatro tipos de autenticação listados, um por linha.</span><span class="sxs-lookup"><span data-stu-id="854de-118">Note that there are four authentication types listed, one per line.</span></span>

8.  <span data-ttu-id="854de-119">Mova a linha que contém o tipo de autenticação TLSClient para a parte superior da lista na seção.</span><span class="sxs-lookup"><span data-stu-id="854de-119">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9.  <span data-ttu-id="854de-120">Salve e feche o arquivo Web. config.</span><span class="sxs-lookup"><span data-stu-id="854de-120">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="854de-121">Inicie um prompt de comando com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="854de-121">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="854de-122">Reinicie o IIS executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="854de-122">Restart IIS by running the following command:</span></span>
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

