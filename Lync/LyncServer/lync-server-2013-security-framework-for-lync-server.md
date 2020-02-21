---
title: 'Lync Server 2013: estrutura de segurança para Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security framework for Lync Server 2013
ms:assetid: 01131e28-b38e-40d9-8524-06725b9c6608
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481316(v=OCS.15)
ms:contentKeyID: 59893866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7871d662d76f47685a58384804dfc6dee3b7b1d2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200907"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="security-framework-for-lync-server-2013"></a>Estrutura de segurança para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-11-08_

Esta seção fornece uma visão geral dos elementos fundamentais que formam a estrutura de segurança do Microsoft Lync Server 2013. Entender como esses elementos funcionam juntos é essencial para tomar decisões informadas sobre como proteger sua implantação específica do Lync Server 2013.

Essas elementos são os seguintes:

  - O AD DS (Serviços de Domínio Active Directory) fornece um repositório back-end confiável para contas de usuário e recursos de rede.

  - O RBAC (controle de acesso baseado em função) permite delegar tarefas administrativas enquanto mantém altos padrões de segurança.

  - A infraestrutura de chave pública (PKI) usa certificados emitidos por autoridades de certificação (CAs) confiáveis para autenticar servidores e garantir a integridade dos dados.

  - Os protocolos TLS, HTTP sobre SSL (HTTPS) e MTLS (TLS mútuo) permitem a autenticação de ponto de extremidade e a criptografia de mensagens instantâneas. Os fluxos de compartilhamento ponto a ponto de áudio, vídeo e aplicativo são criptografados usando SRTP (Secure Real-Time Transport Protocol).

  - Protocolos padrão do setor para autenticação do usuário, quando possível.

  - O Windows PowerShell fornece recursos de segurança habilitados por padrão, de modo que os usuários não possam executar scripts com facilidade ou sem saber.

Esses elementos de segurança fundamentais funcionam em conjunto para definir usuários, servidores, conexões e operações confiáveis para ajudar a garantir uma base segura para o Lync Server 2013.

<div>

## <a name="in-this-section"></a>Nesta seção

Os tópicos desta seção descrevem como cada um desses elementos fundamentais funciona para melhorar a segurança da infraestrutura do Lync Server.

  - [Serviços de domínio do Active Directory para o Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [Controle de acesso baseado em função (RBAC) para o Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md)

  - [Infraestrutura de chave pública do Lync Server 2013](lync-server-2013-public-key-infrastructure.md)

  - [TLS e MTLS para o Lync Server 2013](lync-server-2013-tls-and-mtls.md)

  - [Criptografia para o Lync Server 2013](lync-server-2013-encryption.md)

  - [Autenticação de usuário e cliente para o Lync Server 2013](lync-server-2013-user-and-client-authentication.md)

  - [Ferramentas de gerenciamento do Windows PowerShell e do Lync Server 2013](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

