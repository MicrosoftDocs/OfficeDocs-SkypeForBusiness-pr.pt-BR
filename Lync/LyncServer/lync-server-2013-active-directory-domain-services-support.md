---
title: 'Lync Server 2013: Suporte a Serviços de Domínio Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services support
ms:assetid: aeb62d5e-e424-473a-b795-9452150c98dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412831(v=OCS.15)
ms:contentKeyID: 48185136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32e1bce2546512900efb0b5ecd1256a97adde41e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737011"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-support-in-lync-server-2013"></a>Suporte a Serviços de Domínio Active Directory no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-11-07_

O Lync Server 2013 usa o repositório de gerenciamento central para armazenar dados de configuração para servidores e serviços, em vez de confiar nos serviços de domínio Active Directory para essas informações, como no passado. O Lync Server 2013 ainda armazena o seguinte no AD DS:

  - **Extensões de esquema**
    
      - Extensões de objetos de usuário
    
      - Extensões para as classes do Lync Server 2010 e do Office Communications Server 2007 R2 para manter a compatibilidade com versões anteriores do suporte

  - **Dados** (armazenados no esquema estendido do Lync Server 2013 e em classes existentes)
    
      - URI do SIP do usuário e outras configurações de usuário
    
      - Objetos de contato para aplicativos (por exemplo, o aplicativo do grupo de resposta e o aplicativo do atendente de conferência)
    
      - Dados publicados para compatibilidade com versões anteriores
    
      - Um SCP (ponto de controle de serviço) para o repositório de gerenciamento central
    
      - Conta de autenticação Kerberos (um objeto de computador opcional)

Esta seção descreve os requisitos de suporte do AD DS para o Lync Server 2013. Para obter detalhes sobre o suporte à topologia, consulte [topologias do Active Directory com suporte no Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) na documentação de suporte.

<div>

## <a name="supported-domain-controller-operating-systems"></a>Sistemas operacionais do controlador de domínio com suporte

O Lync Server 2013 oferece suporte a controladores de domínio que executam os seguintes sistemas operacionais:

  - Sistema operacional Windows Server 2012 R2

  - Sistema operacional Windows Server 2012

  - Sistema operacional Windows Server 2008 R2

  - Sistema operacional Windows Server 2008

  - Windows Server 2008 Enterprise 32-bit

  - As versões de 32 bits ou 64 bits do sistema operacional Windows Server 2003 R2

  - As versões de 32 bits ou 64 bits do sistema operacional Windows Server 2003

</div>

<div>

## <a name="forest-and-domain-functional-level"></a>Nível funcional da floresta e do domínio

Você deve disparar todos os domínios nos quais implanta o Lync Server 2013 em um nível funcional de domínio do Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 ou pelo menos Windows Server 2003.

Todas as florestas nas quais você implanta o Lync Server 2013 devem ser elevadas para um nível funcional de floresta do Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 ou pelo menos Windows Server 2003.

</div>

<div>

## <a name="support-for-read-only-domain-controllers"></a>Suporte para controladores de domínio somente leitura

O Lync Server 2013 dá suporte a implantações de serviços de domínio Active Directory que incluem controladores de domínio somente leitura ou servidores de catálogo global somente leitura, desde que existam controladores de domínio graváveis disponíveis.

</div>

<div>

## <a name="domain-names"></a>Nomes de domínio

O Lync Server não dá suporte a domínios com rótulo único. Por exemplo, uma floresta com um domínio raiz chamado **contoso. local** tem suporte, mas não há suporte para um domínio raiz chamado **local** . Para obter detalhes, consulte o artigo 300684 da base de dados de conhecimento Microsoft, "informações sobre como configurar o Windows para domínios com [http://go.microsoft.com/fwlink/p/?linkId=143752](http://go.microsoft.com/fwlink/p/?linkid=143752)nomes DNS de rótulo único" em.

<div>


> [!NOTE]  
> O Lync Server não permite a renomeação de domínios. Se você precisar renomear um domínio onde o Lync Server está implantado, primeiro você precisa desinstalar o Lync Server, depois renomear o domínio e depois reinstalar o Lync Server.



</div>

</div>

<div>

## <a name="locked-down-adds-environments"></a>Ambientes AD DS bloqueados

Em um ambiente do AD DS bloqueado, usuários e objetos de computador geralmente são colocados em unidades organizacionais específicas (UOs) com herança de permissões desabilitada para ajudar a proteger a delegação administrativa e habilitar o uso de objetos de política de grupo (GPOs) para aplicar políticas de segurança. O Lync Server 2013 pode ser implantado em um ambiente do Active Directory bloqueado. Para obter detalhes sobre o que é necessário para implantar o Lync Server em um ambiente bloqueado, consulte [preparando os serviços de domínio do Active Directory bloqueados no Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) na documentação de implantação.

</div>

</div>

<span> </span>

</div>

</div>

</div>

