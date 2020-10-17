---
title: 'Lync Server 2013: suporte aos serviços de domínio do Active Directory'
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
ms.openlocfilehash: 44f427486756895f1bff5330075f4c323f944afd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529628"
---
# <a name="active-directory-domain-services-support-in-lync-server-2013"></a>Suporte aos serviços de domínio do Active Directory no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-11-07_

O Lync Server 2013 usa o repositório de gerenciamento central para armazenar dados de configuração para servidores e serviços, em vez de confiar nos serviços de domínio do Active Directory para essas informações, como no passado. O Lync Server 2013 ainda armazena o seguinte no AD DS:

  - **Extensões de esquema**
    
      - Extensões do objeto do usuário
    
      - Extensões para o Lync Server 2010 e o Office Communications Server 2007 R2 classes para manter a compatibilidade com versões anteriores com suporte

  - **Dados** (armazenados no esquema estendido do Lync Server 2013 e em classes existentes)
    
      - URI do SIP do usuário e outras configurações do usuário
    
      - Objetos de contato para aplicativos (por exemplo, o aplicativo de grupo de resposta e o aplicativo de atendedor de conferência)
    
      - Dados publicados para compatibilidade com versões anteriores
    
      - Um ponto de controle de serviço (SCP) para o repositório de gerenciamento central
    
      - Conta de autenticação Kerberos (um objeto de computador opcional)

Esta seção descreve os requisitos de suporte do AD DS para o Lync Server 2013. Para obter detalhes sobre o suporte à topologia, consulte [topologias do Active Directory com suporte no Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) na documentação de suporte.

<div>

## <a name="supported-domain-controller-operating-systems"></a>Sistemas operacionais do controlador de domínio com suporte

O Lync Server 2013 suporta controladores de domínio executando os seguintes sistemas operacionais:

  - Sistema operacional Windows Server 2012 R2

  - Sistema operacional Windows Server 2012

  - Windows Server 2008 R2 operating system

  - Sistema operacional Windows Server 2008

  - Windows Server 2008 Enterprise de 32 bits

  - As versões de 32 bits ou 64 bits do sistema operacional Windows Server 2003 R2

  - As versões de 32 bits ou 64 bits do sistema operacional Windows Server 2003

</div>

<div>

## <a name="forest-and-domain-functional-level"></a>Nível funcional de floresta e domínio

Você deve aumentar todos os domínios nos quais o Lync Server 2013 é implantado em um nível funcional de domínio do Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 ou pelo menos Windows Server 2003.

Todas as florestas nas quais você implanta o Lync Server 2013 devem ser elevadas para um nível funcional de floresta do Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 ou pelo menos Windows Server 2003.

</div>

<div>

## <a name="support-for-read-only-domain-controllers"></a>Suporte para controladores de domínio Read-Only

O Lync Server 2013 oferece suporte a implantações de serviços de domínio do Active Directory que incluem controladores de domínio somente leitura ou servidores de catálogo global somente leitura, desde que haja controladores de domínio graváveis disponíveis.

</div>

<div>

## <a name="domain-names"></a>Nomes de domínio

O Lync Server não dá suporte a domínios com rótulo único. Por exemplo, uma floresta com um domínio raiz chamado **contoso.local** é suportado, mas um domínio raiz chamado **local** não é suportado. Para obter detalhes, consulte o artigo 300684 da base de dados de conhecimento da Microsoft, "informações sobre como configurar o Windows para domínios com nomes DNS de rótulo único" em [https://go.microsoft.com/fwlink/p/?linkId=143752](https://go.microsoft.com/fwlink/p/?linkid=143752) .

<div>


> [!NOTE]  
> O Lync Server não dá suporte à renomeação de domínios. Se for necessário renomear um domínio em que o Lync Server está implantado, primeiro você precisa desinstalar o Lync Server, renomear o domínio e, em seguida, reinstalar o Lync Server.



</div>

</div>

<div>

## <a name="locked-down-adds-environments"></a>Ambientes AD DS bloqueados

Em um ambiente do AD DS bloqueado, os usuários e os objetos de computador costumam ser colocados em unidades organizacionais (UOs) específicas com herança de permissões desabilitada para ajudar a proteger a delegação administrativa e habilitar o uso de GPOs (objetos de política de grupo) para impor políticas de segurança. O Lync Server 2013 pode ser implantado em um ambiente do Active Directory bloqueado. Para obter detalhes sobre o que é necessário para implantar o Lync Server em um ambiente bloqueado, consulte [preparação de serviços de domínio do Active Directory bloqueados no Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) na documentação de implantação.

</div>

</div>

<span> </span>

</div>

</div>

</div>

