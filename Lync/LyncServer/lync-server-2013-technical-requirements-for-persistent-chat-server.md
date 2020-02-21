---
title: 'Lync Server 2013: requisitos técnicos para o servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Persistent Chat Server
ms:assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398495(v=OCS.15)
ms:contentKeyID: 48184383
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75c5bd99e487aa596bdf3b32db77d8deb2cfab9e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194784"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-persistent-chat-server-in-lync-server-2013"></a>Requisitos técnicos para o servidor de chat persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-01-06_

Cada computador que hospeda o servidor de chat persistente deve ter acesso a uma topologia existente do Lync Server 2013 com os seguintes componentes:

  - **Lync Server 2013, servidor front-end.**  O servidor front-end é a base para o roteamento do protocolo SIP, que faz a comunicação entre os computadores que executam o servidor de chat persistente e a funcionalidade de chat persistente possível. Antes de começar a implantar o servidor de chat persistente, verifique a implantação do Lync Server 2013, Standard Edition ou de um pool de front-ends do Lync Server e de qualquer outro computador interno executando o Lync Server, conforme apropriado para sua organização.

As seções a seguir descrevem os requisitos específicos para o servidor de chat persistente e o banco de dados que armazena os dados de chat persistente.

<div>

## <a name="persistent-chat-server-requirements"></a>Requisitos do servidor de chat persistente

Para obter detalhes sobre o hardware recomendado para implantar o Lync Server e a versão mais recente do servidor de chat persistente, consulte [Server Hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) na documentação de suporte.

Para obter detalhes sobre o servidor e as ferramentas de suporte do sistema operacional para Lync Server e servidor de chat persistente, consulte [Server and Tools Operating System support in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) na documentação de suporte.

Para obter detalhes sobre o software adicional necessário para a implantação do servidor de chat persistente, consulte a tabela a seguir.

### <a name="persistent-chat-server-software-prerequisites"></a>Pré-requisitos de software do servidor de chat persistente

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Software</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Serviço de Enfileiramento de Mensagens</p></td>
<td><p>Usado pelo servidor de chat persistente e pelo serviço de conformidade de chat persistente, se implantado.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-database-requirements"></a>Requisitos de banco de dados do servidor de chat persistente

O servidor de chat persistente usa o banco de dados de chat persistente para armazenar o histórico de chat, configuração e dados de provisionamento do usuário. Opcionalmente, ele usa o banco de dados de conformidade de chat persistente para armazenar dados de conformidade.

<div>


> [!IMPORTANT]  
> O banco de dados de chat persistente (MGC) e o banco de dados de conformidade (mgccomp) podem estar localizados na mesma instância do SQL Server ou em servidores SQL diferentes.



</div>

Para preparar uma plataforma de servidor de banco de dados, certifique-se de que cada computador atende aos requisitos de hardware e instale o software de pré-requisito.

A plataforma de servidor para os servidores de banco de dados de chat persistente requer o mesmo hardware que o servidor de banco de dados back-end do Lync Server. Para obter detalhes, consulte [Server Hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) na documentação de suporte.

No servidor de banco de dados, certifique-se de que um dos seguintes aplicativos de software está instalado:

  - Microsoft SQL Server 2012. Para obter detalhes sobre como instalar o Microsoft SQL Server 2012, consulte "instalar o SQL Server 2012 [https://go.microsoft.com/fwlink/p/?LinkID=248559](https://go.microsoft.com/fwlink/p/?linkid=248559)" em.

  - Microsoft SQL Server 2008 R2. Para obter detalhes sobre como instalar o Microsoft SQL Server 2008 R2, consulte "instalação do SQL Server (SQL Server 2008 R2) [https://go.microsoft.com/fwlink/?LinkId=275702](https://go.microsoft.com/fwlink/?linkid=275702)" em.

</div>

<div>

## <a name="persistent-chat-server-certificate-requirements"></a>Requisitos de certificado do servidor de chat persistente

Para obter detalhes sobre a aquisição de certificados, criação do banco de dados do SQL Server e criação de repositórios de arquivos, consulte [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) na documentação de implantação.

</div>

</div>

<span> </span>

</div>

</div>

</div>

