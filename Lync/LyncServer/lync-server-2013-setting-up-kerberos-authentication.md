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
ms.openlocfilehash: 8c644dd613b3186b314e8fc78b42197709286200
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="b36d2-102">Configurando a autenticação Kerberos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b36d2-102">Setting up Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b36d2-103">_**Tópico da última modificação:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="b36d2-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="b36d2-104">O Lync Server 2013 dá suporte à autenticação NTLM e Kerberos para serviços Web.</span><span class="sxs-lookup"><span data-stu-id="b36d2-104">Lync Server 2013 supports NTLM and Kerberos authentication for Web Services.</span></span> <span data-ttu-id="b36d2-105">O Office Communications Server 2007 e o Office Communications Server 2007 R2 usavam o RTCComponentService padrão e o RTCService como as contas de usuário para executar os pools de aplicativos de serviços Web, permitindo que um SPN (nome da entidade de serviço) seja atribuído ao usuário contas e para atuar como a entidade de autenticação.</span><span class="sxs-lookup"><span data-stu-id="b36d2-105">Office Communications Server 2007 and Office Communications Server 2007 R2 used the default RTCComponentService and RTCService as the user accounts to run the Web Services application pools, allowing for a service principal name (SPN) to be assigned to the user accounts and to act as the authentication principal.</span></span> <span data-ttu-id="b36d2-106">O Lync Server usa o NetworkService para executar serviços Web e o NetworkService não pode ter SPNs atribuídos a ele.</span><span class="sxs-lookup"><span data-stu-id="b36d2-106">Lync Server uses NetworkService to run Web Services and NetworkService cannot have SPNs assigned to it.</span></span>

<span data-ttu-id="b36d2-107">Para solucionar o problema de não ter objetos do Active Directory para manter os SPNs, o painel de controle do Lync Server pode usar objetos de conta de computador para essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="b36d2-107">To solve the issue of not having Active Directory objects to hold the SPNs, Lync Server Control Panel can use computer account objects for this purpose.</span></span> <span data-ttu-id="b36d2-108">Os objetos de conta de computador podem conter os SPNs e não estão sujeitos à expiração da senha, que foi um problema com o uso de contas de usuário em versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="b36d2-108">The computer account objects can hold the SPNs and are not subject to password expiration, which was an issue with using user accounts in previous versions.</span></span>

<span data-ttu-id="b36d2-109">Use cmdlets do Windows PowerShell para configurar os objetos do computador para fornecer autenticação Kerberos.</span><span class="sxs-lookup"><span data-stu-id="b36d2-109">You use Windows PowerShell cmdlets to configure the computer objects to provide Kerberos authentication.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b36d2-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="b36d2-110">In This Section</span></span>

  - [<span data-ttu-id="b36d2-111">Pré-requisitos para habilitar autenticação Kerberos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b36d2-111">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [<span data-ttu-id="b36d2-112">Criar uma conta de autenticação Kerberos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b36d2-112">Create a Kerberos authentication account in Lync Server 2013</span></span>](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [<span data-ttu-id="b36d2-113">Atribuir uma conta de autenticação Kerberos a um site no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b36d2-113">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [<span data-ttu-id="b36d2-114">Configurando senhas da conta de autenticação Kerberos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b36d2-114">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [<span data-ttu-id="b36d2-115">No Lync Server 2013, adicionar autenticação Kerberos a outros sites</span><span class="sxs-lookup"><span data-stu-id="b36d2-115">In Lync Server 2013 add Kerberos authentication to other sites</span></span>](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [<span data-ttu-id="b36d2-116">No Lync Server 2013, remover autenticação Kerberos de um site</span><span class="sxs-lookup"><span data-stu-id="b36d2-116">In Lync Server 2013 remove Kerberos authentication from a site</span></span>](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [<span data-ttu-id="b36d2-117">Testando e relatando status e atribuição de autenticação Kerberos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b36d2-117">Testing and reporting the status and assignment of Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

