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
ms.openlocfilehash: 1a2b58d34c1ed1f899e0daac8c1bb0132b1a22d7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764899"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-framework-for-lync-server-2013"></a>Estrutura de segurança do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-11-08_

Esta seção fornece uma visão geral dos elementos fundamentais que formam a estrutura de segurança do Microsoft Lync Server 2013. Entender como esses elementos funcionam juntos é essencial para tomar decisões conscientes sobre como proteger sua implantação do Lync Server 2013 específica.

Esses elementos são:

  - O AD DS (serviços de domínio Active Directory) fornece um único repositório de back-end confiável para contas de usuário e recursos de rede.

  - O controle de acesso baseado em função (RBAC) permite delegar tarefas administrativas enquanto mantém altos padrões de segurança.

  - A infraestrutura de chave pública (PKI) utiliza certificados emitidos por autoridades de certificação (CAs) confiáveis para autenticar servidores e garantir a integridade de dados.

  - A segurança da camada de transporte (TLS), HTTPS sobre SSL (HTTPS) e TLS mútuo (MTLS) possibilitam a autenticação de ponto de extremidade e criptografia IM. Os fluxos de áudio e vídeo ponto a ponto e de compartilhamento de aplicativos são criptografados utilizando protocolo de transporte em tempo real seguro (SRTP).

  - Protocolos padrão do setor para autenticação do usuário, onde possível.

  - O Windows PowerShell fornece recursos de segurança habilitados por padrão para que os usuários não possam executar scripts de forma fácil ou desconhecida.

Esses elementos de segurança fundamentais trabalham em conjunto para definir usuários, servidores, conexões e operações confiáveis para ajudar a garantir uma base segura para o Lync Server 2013.

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

