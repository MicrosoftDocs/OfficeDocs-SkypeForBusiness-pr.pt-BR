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
ms.openlocfilehash: fc4f354d985ed9e0fc85909e232e06e7c34dd593
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509648"
---
# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a>Configurando a autenticação Kerberos no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

O Lync Server 2013 oferece suporte à autenticação NTLM e Kerberos para serviços Web. O Office Communications Server 2007 e o Office Communications Server 2007 R2 usavam o RTCComponentService e o RTCService padrão como as contas de usuário para executar os pools de aplicativos de serviços Web, permitindo que um nome de entidade de serviço (SPN) seja atribuído às contas de usuário e atue como a entidade de autenticação. O Lync Server usa NetworkService para executar serviços Web e NetworkService não pode ter SPNs atribuídos a ele.

Para resolver o problema de não ter objetos do Active Directory para manter os SPNs, o painel de controle do Lync Server pode usar objetos de conta de computador para essa finalidade. Os objetos de conta de computador podem armazenar os SPNs e não estão sujeitos à expiração da senha, que foi um problema com o uso de contas de usuário em versões anteriores.

Use os cmdlets do Windows PowerShell para configurar os objetos de computador para fornecer autenticação Kerberos.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Pré-requisitos para habilitar a autenticação Kerberos no Lync Server 2013](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [Criar uma conta de autenticação Kerberos no Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [Atribuir uma conta de autenticação Kerberos a um site no Lync Server 2013](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [Configurando senhas da conta de autenticação Kerberos no Lync Server 2013](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [No Lync Server 2013, adicione autenticação Kerberos a outros sites](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [No Lync Server 2013 remover a autenticação Kerberos de um site](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [Testando e relatando o status e a atribuição de autenticação Kerberos no Lync Server 2013](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

