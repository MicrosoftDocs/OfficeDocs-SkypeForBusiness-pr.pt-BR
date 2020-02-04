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
ms.openlocfilehash: c7fe9587e85ad300a212e4a8199fa4a8a48d1877
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a><span data-ttu-id="3bc65-102">Configurando o AD FS 2,0 para dar suporte à autenticação de cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bc65-102">Configuring AD FS 2.0 to support client authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3bc65-103">_**Tópico da última modificação:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="3bc65-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="3bc65-104">Há dois tipos possíveis de autenticação que podem ser configurados para permitir que o AD FS 2.0 suporte autenticações utilizando cartões inteligentes:</span><span class="sxs-lookup"><span data-stu-id="3bc65-104">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

  - <span data-ttu-id="3bc65-105">Autenticação baseada em formulário (FBA)</span><span class="sxs-lookup"><span data-stu-id="3bc65-105">Forms-based authentication (FBA)</span></span>

  - <span data-ttu-id="3bc65-106">Autenticação de Cliente de Segurança na Camada de Transporte</span><span class="sxs-lookup"><span data-stu-id="3bc65-106">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="3bc65-107">Utilizando a autenticação baseada em formulários, você pode desenvolver uma página da Web que permite que os usuários autentiquem usando seus nomes de usuário/senhas ou usando o cartão inteligente e o PIN.</span><span class="sxs-lookup"><span data-stu-id="3bc65-107">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="3bc65-108">Este tópico tem como foco como implementar a Autenticação de Cliente de Segurança na Camada de Transporte com o AD FS 2.0.</span><span class="sxs-lookup"><span data-stu-id="3bc65-108">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="3bc65-109">Para obter mais informações sobre os tipos de autenticação do AD FS 2,0, consulte AD FS 2,0: como alterar o tipo [http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384)de autenticação local em.</span><span class="sxs-lookup"><span data-stu-id="3bc65-109">For more information about AD FS 2.0 authentication types, see AD FS 2.0: How to Change the Local Authentication Type at [http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384).</span></span>

<div>


<span data-ttu-id="3bc65-110">**Para configurar o AD FS 2.0 para suportar a autenticação de cliente**</span><span class="sxs-lookup"><span data-stu-id="3bc65-110">**To Configure AD FS 2.0 to Support Client Authentication**</span></span>

1.  <span data-ttu-id="3bc65-111">Faça logon no computador do AD FS 2.0 utilizando uma conta de Administrador de Domínio.</span><span class="sxs-lookup"><span data-stu-id="3bc65-111">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="3bc65-112">Inicie o Windows Explorer.</span><span class="sxs-lookup"><span data-stu-id="3bc65-112">Launch Windows Explorer.</span></span>

3.  <span data-ttu-id="3bc65-113">Navegue até C:\\Inetpub\\ADFS\\ls</span><span class="sxs-lookup"><span data-stu-id="3bc65-113">Browse to C:\\inetpub\\adfs\\ls</span></span>

4.  <span data-ttu-id="3bc65-114">Faça uma cópia de backup do arquivo web.config existente.</span><span class="sxs-lookup"><span data-stu-id="3bc65-114">Make a backup copy of the existing web.config file.</span></span>

5.  <span data-ttu-id="3bc65-115">Abra o arquivo web.config existente utilizando o Bloco de Notas.</span><span class="sxs-lookup"><span data-stu-id="3bc65-115">Open the existing web.config file using Notepad.</span></span>

6.  <span data-ttu-id="3bc65-116">Na barra de Menu, selecione **Editar** e, em seguida, selecione **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="3bc65-116">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7.  <span data-ttu-id="3bc65-117">Procure por \*\* \<localAuthenticationTypes\>\*\*.</span><span class="sxs-lookup"><span data-stu-id="3bc65-117">Search for **\<localAuthenticationTypes\>**.</span></span>
    
    <span data-ttu-id="3bc65-118">Observe que há quatro tipos de autenticação listados, um por linha.</span><span class="sxs-lookup"><span data-stu-id="3bc65-118">Note that there are four authentication types listed, one per line.</span></span>

8.  <span data-ttu-id="3bc65-119">Mova para a linha que contém o tipo de autenticação TLSClient para o topo da lista na seção.</span><span class="sxs-lookup"><span data-stu-id="3bc65-119">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9.  <span data-ttu-id="3bc65-120">Salve e Feche o arquivo web.config.</span><span class="sxs-lookup"><span data-stu-id="3bc65-120">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="3bc65-121">Inicie um Prompt de Comando com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="3bc65-121">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="3bc65-122">Reinicie o IIS executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3bc65-122">Restart IIS by running the following command:</span></span>
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

