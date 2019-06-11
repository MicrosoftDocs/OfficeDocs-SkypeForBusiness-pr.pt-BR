---
title: 'Lync Server 2013: Configurando a autenticação Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up Kerberos authentication
ms:assetid: dd8009ef-6265-4cc0-b2c7-e474cd1f4b09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398976(v=OCS.15)
ms:contentKeyID: 48185601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86526b40ee837866cdf0e3b016a8e4e627ca2eef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a>Configurando a autenticação Kerberos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

O Lync Server 2013 dá suporte à autenticação NTLM e Kerberos para serviços Web. O Office Communications Server 2007 e o Office Communications Server 2007 R2 usavam o RTCComponentService padrão e o RTCService como as contas de usuário para executar os pools de aplicativos de serviços Web, permitindo que um SPN (nome da entidade de serviço) seja atribuído ao usuário contas e para atuar como a entidade de autenticação. O Lync Server usa o NetworkService para executar serviços Web e o NetworkService não pode ter SPNs atribuídos a ele.

Para solucionar o problema de não ter objetos do Active Directory para manter os SPNs, o painel de controle do Lync Server pode usar objetos de conta de computador para essa finalidade. Os objetos de conta de computador podem conter os SPNs e não estão sujeitos à expiração da senha, que foi um problema com o uso de contas de usuário em versões anteriores.

Use cmdlets do Windows PowerShell para configurar os objetos do computador para fornecer autenticação Kerberos.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Pré-requisitos para habilitar autenticação Kerberos no Lync Server 2013](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [Criar uma conta de autenticação Kerberos no Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [Atribuir uma conta de autenticação Kerberos a um site no Lync Server 2013](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [Configurando senhas da conta de autenticação Kerberos no Lync Server 2013](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [No Lync Server 2013, adicionar autenticação Kerberos a outros sites](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [No Lync Server 2013, remover autenticação Kerberos de um site](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [Testando e relatando status e atribuição de autenticação Kerberos no Lync Server 2013](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

