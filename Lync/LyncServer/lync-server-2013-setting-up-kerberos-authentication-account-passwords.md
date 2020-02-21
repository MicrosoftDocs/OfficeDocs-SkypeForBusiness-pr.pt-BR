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
ms.openlocfilehash: 21ed9f0b5bd8e9aecfb39a7dd9c159857d4b240e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182035"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a>Configurando senhas da conta de autenticação Kerberos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2010-11-03_

Depois de criar o objeto de computador para a conta de autenticação Kerberos, você poderá configurar a senha da conta. Execute o cmdlet do Windows PowerShell para configurar a senha da conta Kerberos em um servidor. É possível definir a senha no objeto criado para a autenticação Kerberos. A senha pode ser definida como um valor conhecido, mas por padrão é uma senha aleatória. A senha está disponível para todas as fontes de autenticação Kerberos que usam a conta. Use os cmdlets do Windows PowerShell para configurar e gerenciar senhas de conta Kerberos.

<div>


> [!NOTE]  
> O objeto de conta Kerberos é um objeto de computador, mas usa o parâmetro USERACCOUNT para operações nos cmdlets do Windows PowerShell referenciados. Perceba que isso não é um erro, mas o comportamento pretendido do cmdlet quando usado com a criação e manutenção da conta Kerberos.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Definir uma senha de conta de autenticação Kerberos em um servidor no Lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [Sincronizar uma senha de conta de autenticação Kerberos com o IIS no Lync Server 2013](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

