---
title: 'Lync Server 2013: protegendo e protegendo servidores e aplicativos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting servers and applications for Lync Server 2013
ms:assetid: 9ca2b233-26f1-4d72-96e7-81a82c727806
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518331(v=OCS.15)
ms:contentKeyID: 62625491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3533bcf01338a056bab8c75d1409530fab7c901f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536878"
---
# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a>Proteção e proteção de servidores e aplicativos para o Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-12-05_

Você deve aumentar a segurança do sistema operacional e dos aplicativos de acordo com as práticas recomendadas para esse componente específico. Esta seção descreve como proteger os servidores de aplicativo e usar a Política de Grupo para implementar os bloqueios de segurança.

<div>


> [!NOTE]  
> Você também pode proteger e proteger os bancos de dados usados para a implantação do Microsoft Lync Server 2013. Para obter detalhes, consulte <A href="lync-server-2013-hardening-and-protecting-databases.md">proteção e proteção dos bancos de dados do Lync Server 2013</A>.



</div>

<div>

## <a name="securing-application-servers"></a>Protegendo servidores de aplicativos

No caso dos servidores de aplicativos, a segurança do sistema operacional e do aplicativo deve ser intensificada. Por exemplo, um computador com o Windows Server 2008 dedicado à execução do ISA (Microsoft Internet Security and Acceleration) Server 2006 deve ser protegido sob a perspectiva do sistema operacional e do aplicativo. Minimizar o número de serviços em execução e fornecidos pelo servidor deve ser a meta principal.

</div>

<div>

## <a name="securing-virtual-servers"></a>Protegendo servidores virtuais

Os instantâneos de servidores virtuais contêm cópias dos discos de dados do servidor e também contém despejos de dados na memória, que podem conter dados criptografados confidenciais que estão sujeitos a ataques. Para os servidores de produção implementados usando a virtualização, você deve desabilitar todos os instantâneos de servidor ou gerenciá-los de maneira muito controlada. Para obter detalhes sobre como proteger servidores virtuais do Hyper-V, consulte o guia de segurança do Hyper-V em: [https://go.microsoft.com/fwlink/p/?LinkId=214176](https://go.microsoft.com/fwlink/p/?linkid=214176) .

</div>

<div>

## <a name="group-policy"></a>Política de Grupo

No Windows Server 2008 e no Windows Server 2008 R2, a Política de Grupo fornece gerenciamento da configuração de área de trabalho baseado em diretório. Você pode usar a Política de Grupo para implementar os bloqueios de segurança, definindo as configurações do Computador e Usuário dentro de um GPO (objeto de Política de Grupo) para o seguinte:

  - Políticas baseadas no Registro

  - Segurança

  - Instalação de software

  - Scripts

  - Redirecionamento de pasta

  - Serviços de instalação remota

Para fornecer uma interface de usuário para o administrador configurar essas configurações, os modelos administrativos são fornecidos com versões de sistema operacional, versões de Service Pack e alguns aplicativos, incluindo o Lync Server 2013.

O arquivo Communicator. adm é um modelo administrativo que acompanha o Lync Server 2013, é instalado no diretório% windir% \\ inf \\ e fornece uma interface para as configurações da política de grupo. Cada configuração no Communicator.adm corresponde a uma configuração do Registro que afeta o comportamento do aplicativo.

As configurações podem ser acessadas no GPedit.dll, que, por sua vez, está disponível no console Usuários e Computadores do Active Directory e no GPMC (Console de Gerenciamento de Diretiva de Grupo).

</div>

<div>

## <a name="group-policy-security-settings"></a>Configurações de segurança de Política de Grupo

A Política de Grupo contém as configurações de segurança de um GPO em Configuração do Computador/Configurações do Windows/Configurações de Segurança quando é acessada a partir do GPedit.dll. Você pode importar os modelos de segurança para definir as configurações de segurança do GPO. O guia de segurança do Windows Server 2008 em [https://go.microsoft.com/fwlink/p/?LinkId=145186](https://go.microsoft.com/fwlink/p/?linkid=145186) e o kit de ferramentas de gerenciamento de conformidade de segurança do Windows server 2008 R2 [https://go.microsoft.com/fwlink/p/?LinkId=211882](https://go.microsoft.com/fwlink/p/?linkid=211882) contêm vários exemplos de modelos que podem ser modificados para atender às suas necessidades.

</div>

<div>

## <a name="best-practices"></a>Práticas recomendadas

  - Melhore a segurança de todos os sistemas operacionais e aplicativos do servidor.

  - Proteja os instantâneos de servidor e aumente a segurança de todos os servidores virtuais.

  - Use a Política de Grupo para implementar os bloqueios de segurança.

</div>

</div>

<span> </span>

</div>

</div>

</div>

