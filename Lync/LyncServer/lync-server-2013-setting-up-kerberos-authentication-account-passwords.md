---
title: 'Lync Server 2013: Configurando senhas da conta de autenticação Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication account passwords
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412870(v=OCS.15)
ms:contentKeyID: 48185167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0342c83090dee6cbe021a400acd87e557860518b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a><span data-ttu-id="8054a-102">Configurando senhas da conta de autenticação Kerberos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8054a-102">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8054a-103">_**Última modificação do tópico:** 2010-11-03_</span><span class="sxs-lookup"><span data-stu-id="8054a-103">_**Topic Last Modified:** 2010-11-03_</span></span>

<span data-ttu-id="8054a-104">Depois de criar o objeto de computador para a conta de autenticação Kerberos, você poderá configurar a senha da conta.</span><span class="sxs-lookup"><span data-stu-id="8054a-104">After you create the computer object for the Kerberos authentication account, you can set up the password for the account.</span></span> <span data-ttu-id="8054a-105">Execute o cmdlet do Windows PowerShell para configurar a senha da conta Kerberos em um servidor.</span><span class="sxs-lookup"><span data-stu-id="8054a-105">You run the Windows PowerShell cmdlet for setting the Kerberos account password on one server.</span></span> <span data-ttu-id="8054a-106">É possível definir a senha no objeto criado para a autenticação Kerberos.</span><span class="sxs-lookup"><span data-stu-id="8054a-106">You can set the password on the object that you created for the Kerberos authentication.</span></span> <span data-ttu-id="8054a-107">A senha pode ser definida como um valor conhecido, mas por padrão é uma senha aleatória.</span><span class="sxs-lookup"><span data-stu-id="8054a-107">The password can be set to a known value, but by default is a random password.</span></span> <span data-ttu-id="8054a-108">A senha está disponível para todas as fontes de autenticação Kerberos que usam a conta.</span><span class="sxs-lookup"><span data-stu-id="8054a-108">The password is available to all Kerberos authentication sources that use the account.</span></span> <span data-ttu-id="8054a-109">Use os cmdlets do Windows PowerShell para configurar e gerenciar senhas de conta Kerberos.</span><span class="sxs-lookup"><span data-stu-id="8054a-109">You use Windows PowerShell cmdlets to set up and manage Kerberos account passwords.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8054a-110">O objeto de conta Kerberos é um objeto de computador, mas usa o parâmetro USERACCOUNT para operações nos cmdlets do Windows PowerShell referenciados.</span><span class="sxs-lookup"><span data-stu-id="8054a-110">The Kerberos account object is a computer object, but uses the UserAccount parameter for operations in the Windows PowerShell cmdlets that are referenced.</span></span> <span data-ttu-id="8054a-111">Perceba que isso não é um erro, mas o comportamento pretendido do cmdlet quando usado com a criação e manutenção da conta Kerberos.</span><span class="sxs-lookup"><span data-stu-id="8054a-111">Note that this is not a mistake, but the intended behavior of the cmdlet when used with the Kerberos account creation and maintenance.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8054a-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="8054a-112">In This Section</span></span>

  - [<span data-ttu-id="8054a-113">Definir uma senha de conta de autenticação Kerberos em um servidor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8054a-113">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [<span data-ttu-id="8054a-114">Sincronizar uma senha de conta de autenticação Kerberos com o IIS no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8054a-114">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

