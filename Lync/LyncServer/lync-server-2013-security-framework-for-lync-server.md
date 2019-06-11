---
title: 'Lync Server 2013: estrutura de segurança para Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Security framework for Lync Server 2013
ms:assetid: 01131e28-b38e-40d9-8524-06725b9c6608
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481316(v=OCS.15)
ms:contentKeyID: 59893866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17900e0ca9db8f9dbc1bf66a1bd65aff62d9dd62
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-framework-for-lync-server-2013"></a><span data-ttu-id="97d8e-102">Estrutura de segurança do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97d8e-102">Security framework for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97d8e-103">_**Tópico da última modificação:** 2013-11-08_</span><span class="sxs-lookup"><span data-stu-id="97d8e-103">_**Topic Last Modified:** 2013-11-08_</span></span>

<span data-ttu-id="97d8e-104">Esta seção fornece uma visão geral dos elementos fundamentais que formam a estrutura de segurança do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="97d8e-104">This section provides an overview of the fundamental elements that form the security framework for Microsoft Lync Server 2013.</span></span> <span data-ttu-id="97d8e-105">Entender como esses elementos funcionam juntos é essencial para tomar decisões conscientes sobre como proteger sua implantação do Lync Server 2013 específica.</span><span class="sxs-lookup"><span data-stu-id="97d8e-105">Understanding how these elements work together is essential to making informed decisions about securing your particular Lync Server 2013 deployment.</span></span>

<span data-ttu-id="97d8e-106">Esses elementos são:</span><span class="sxs-lookup"><span data-stu-id="97d8e-106">These elements are as follows:</span></span>

  - <span data-ttu-id="97d8e-107">O AD DS (serviços de domínio Active Directory) fornece um único repositório de back-end confiável para contas de usuário e recursos de rede.</span><span class="sxs-lookup"><span data-stu-id="97d8e-107">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>

  - <span data-ttu-id="97d8e-108">O controle de acesso baseado em função (RBAC) permite delegar tarefas administrativas enquanto mantém altos padrões de segurança.</span><span class="sxs-lookup"><span data-stu-id="97d8e-108">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>

  - <span data-ttu-id="97d8e-109">A infraestrutura de chave pública (PKI) utiliza certificados emitidos por autoridades de certificação (CAs) confiáveis para autenticar servidores e garantir a integridade de dados.</span><span class="sxs-lookup"><span data-stu-id="97d8e-109">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>

  - <span data-ttu-id="97d8e-p102">A segurança da camada de transporte (TLS), HTTPS sobre SSL (HTTPS) e TLS mútuo (MTLS) possibilitam a autenticação de ponto de extremidade e criptografia IM. Os fluxos de áudio e vídeo ponto a ponto e de compartilhamento de aplicativos são criptografados utilizando protocolo de transporte em tempo real seguro (SRTP).</span><span class="sxs-lookup"><span data-stu-id="97d8e-p102">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>

  - <span data-ttu-id="97d8e-112">Protocolos padrão do setor para autenticação do usuário, onde possível.</span><span class="sxs-lookup"><span data-stu-id="97d8e-112">Industry-standard protocols for user authentication, where possible.</span></span>

  - <span data-ttu-id="97d8e-113">O Windows PowerShell fornece recursos de segurança habilitados por padrão para que os usuários não possam executar scripts de forma fácil ou desconhecida.</span><span class="sxs-lookup"><span data-stu-id="97d8e-113">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>

<span data-ttu-id="97d8e-114">Esses elementos de segurança fundamentais trabalham em conjunto para definir usuários, servidores, conexões e operações confiáveis para ajudar a garantir uma base segura para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="97d8e-114">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Lync Server 2013.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="97d8e-115">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="97d8e-115">In This Section</span></span>

<span data-ttu-id="97d8e-116">Os tópicos desta seção descrevem como cada um desses elementos fundamentais funciona para melhorar a segurança da infraestrutura do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="97d8e-116">The topics in this section describe how each of these fundamental elements works to enhance the security of your Lync Server infrastructure.</span></span>

  - [<span data-ttu-id="97d8e-117">Serviços de domínio do Active Directory para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97d8e-117">Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [<span data-ttu-id="97d8e-118">Controle de acesso baseado em função (RBAC) para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97d8e-118">Role-based access control (RBAC) for Lync Server 2013</span></span>](lync-server-2013-role-based-access-control-rbac.md)

  - [<span data-ttu-id="97d8e-119">Infraestrutura de chave pública do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97d8e-119">Public Key Infrastructure for Lync Server 2013</span></span>](lync-server-2013-public-key-infrastructure.md)

  - [<span data-ttu-id="97d8e-120">TLS e MTLS para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97d8e-120">TLS and MTLS for Lync Server 2013</span></span>](lync-server-2013-tls-and-mtls.md)

  - [<span data-ttu-id="97d8e-121">Criptografia para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97d8e-121">Encryption for Lync Server 2013</span></span>](lync-server-2013-encryption.md)

  - [<span data-ttu-id="97d8e-122">Autenticação de usuário e cliente para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97d8e-122">User and client authentication for Lync Server 2013</span></span>](lync-server-2013-user-and-client-authentication.md)

  - [<span data-ttu-id="97d8e-123">Ferramentas de gerenciamento do Windows PowerShell e do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97d8e-123">Windows PowerShell and Lync Server 2013 management tools</span></span>](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

