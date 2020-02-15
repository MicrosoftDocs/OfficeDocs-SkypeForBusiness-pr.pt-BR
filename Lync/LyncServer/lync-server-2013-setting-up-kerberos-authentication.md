---
title: 'Lync Server 2013: Configurando a autenticação Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication
ms:assetid: dd8009ef-6265-4cc0-b2c7-e474cd1f4b09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398976(v=OCS.15)
ms:contentKeyID: 48185601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46e419b1f694965518ac505b103de599870e5049
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046514"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="066ab-102">Configurando a autenticação Kerberos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="066ab-102">Setting up Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="066ab-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="066ab-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="066ab-104">O Lync Server 2013 oferece suporte à autenticação NTLM e Kerberos para serviços Web.</span><span class="sxs-lookup"><span data-stu-id="066ab-104">Lync Server 2013 supports NTLM and Kerberos authentication for Web Services.</span></span> <span data-ttu-id="066ab-105">O Office Communications Server 2007 e o Office Communications Server 2007 R2 usavam o RTCComponentService e o RTCService padrão como as contas de usuário para executar os pools de aplicativos de serviços Web, permitindo que um nome de entidade de serviço (SPN) seja atribuído ao usuário contas e atuar como entidade de autenticação.</span><span class="sxs-lookup"><span data-stu-id="066ab-105">Office Communications Server 2007 and Office Communications Server 2007 R2 used the default RTCComponentService and RTCService as the user accounts to run the Web Services application pools, allowing for a service principal name (SPN) to be assigned to the user accounts and to act as the authentication principal.</span></span> <span data-ttu-id="066ab-106">O Lync Server usa NetworkService para executar serviços Web e NetworkService não pode ter SPNs atribuídos a ele.</span><span class="sxs-lookup"><span data-stu-id="066ab-106">Lync Server uses NetworkService to run Web Services and NetworkService cannot have SPNs assigned to it.</span></span>

<span data-ttu-id="066ab-107">Para resolver o problema de não ter objetos do Active Directory para manter os SPNs, o painel de controle do Lync Server pode usar objetos de conta de computador para essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="066ab-107">To solve the issue of not having Active Directory objects to hold the SPNs, Lync Server Control Panel can use computer account objects for this purpose.</span></span> <span data-ttu-id="066ab-108">Os objetos de conta de computador podem armazenar os SPNs e não estão sujeitos à expiração da senha, que foi um problema com o uso de contas de usuário em versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="066ab-108">The computer account objects can hold the SPNs and are not subject to password expiration, which was an issue with using user accounts in previous versions.</span></span>

<span data-ttu-id="066ab-109">Use os cmdlets do Windows PowerShell para configurar os objetos de computador para fornecer autenticação Kerberos.</span><span class="sxs-lookup"><span data-stu-id="066ab-109">You use Windows PowerShell cmdlets to configure the computer objects to provide Kerberos authentication.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="066ab-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="066ab-110">In This Section</span></span>

  - [<span data-ttu-id="066ab-111">Pré-requisitos para habilitar a autenticação Kerberos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="066ab-111">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [<span data-ttu-id="066ab-112">Criar uma conta de autenticação Kerberos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="066ab-112">Create a Kerberos authentication account in Lync Server 2013</span></span>](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [<span data-ttu-id="066ab-113">Atribuir uma conta de autenticação Kerberos a um site no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="066ab-113">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [<span data-ttu-id="066ab-114">Configurando senhas da conta de autenticação Kerberos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="066ab-114">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [<span data-ttu-id="066ab-115">No Lync Server 2013, adicione autenticação Kerberos a outros sites</span><span class="sxs-lookup"><span data-stu-id="066ab-115">In Lync Server 2013 add Kerberos authentication to other sites</span></span>](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [<span data-ttu-id="066ab-116">No Lync Server 2013 remover a autenticação Kerberos de um site</span><span class="sxs-lookup"><span data-stu-id="066ab-116">In Lync Server 2013 remove Kerberos authentication from a site</span></span>](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [<span data-ttu-id="066ab-117">Testando e relatando o status e a atribuição de autenticação Kerberos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="066ab-117">Testing and reporting the status and assignment of Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

