---
title: 'Lync Server 2013: Protegendo servidores e aplicativos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardening and protecting servers and applications for Lync Server 2013
ms:assetid: 9ca2b233-26f1-4d72-96e7-81a82c727806
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518331(v=OCS.15)
ms:contentKeyID: 62625491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00fea9bd192dedaf16567209798f12c7bff23e6a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829090"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a>Protegendo servidores e aplicativos para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-12-05_

Você deve proteger e proteger o sistema operacional e os aplicativos de acordo com as práticas recomendadas para esse componente específico. Esta seção descreve como otimizar a segurança dos servidores de aplicativos e usar a política de grupo para implementar bloqueios de segurança.

<div>


> [!NOTE]  
> Você também pode proteger e proteger os bancos de dados usados para a implantação do Microsoft Lync Server 2013. Para obter detalhes, consulte <A href="lync-server-2013-hardening-and-protecting-databases.md">otimizando a proteção e protegendo os bancos de dados do Lync Server 2013</A>.



</div>

<div>

## <a name="securing-application-servers"></a>Proteger servidores de aplicativos

Para servidores de aplicativos, o sistema operacional e o aplicativo devem ser protegidos. Por exemplo, um computador com Windows Server 2008 dedicado a executar o Microsoft Internet Security and Acceleration (ISA) Server 2006 deve ser protegido do sistema operacional e da perspectiva do aplicativo. Minimizar o número de serviços em execução e fornecido pelo servidor deve ser um objetivo principal.

</div>

<div>

## <a name="securing-virtual-servers"></a>Protegendo servidores virtuais

Instantâneos do servidor virtual contêm cópias dos discos de dados do servidor e também contêm despejos de dados na memória, que podem conter dados de criptografia confidenciais que podem levar a ataques. Para servidores de produção implementados usando a virtualização, você deve desabilitar todos os instantâneos do servidor ou gerenciá-los de forma bem controlada. Para obter detalhes sobre como proteger servidores virtuais Hyper-V, consulte o guia de segurança do Hyper- [http://go.microsoft.com/fwlink/p/?LinkId=214176](http://go.microsoft.com/fwlink/p/?linkid=214176)v em:.

</div>

<div>

## <a name="group-policy"></a>Política de grupo

No Windows Server 2008 e no Windows Server 2008 R2, a política de grupo fornece o gerenciamento de configuração da área de trabalho baseado em diretório. Você pode usar a política de grupo para implementar bloqueios de segurança definindo configurações de computador e de usuário em um objeto de política de grupo (GPO) para o seguinte:

  - Políticas baseadas no registro

  - Segurança

  - Instalação do software

  - Escritas

  - Redirecionamento de pastas

  - Serviços de instalação remota

Para fornecer uma interface do usuário para o administrador definir essas configurações, os modelos administrativos são fornecidos com versões do sistema operacional, versões do Service Pack e alguns aplicativos, incluindo o Lync Server 2013.

O arquivo. adm do Communicator é um modelo administrativo que acompanha o Lync Server 2013, é instalado no diretório% windir\\%\\ inf e fornece uma interface para as configurações de política de grupo. Cada configuração no Communicator. adm corresponde a uma configuração no registro que afeta o comportamento do aplicativo.

As configurações podem ser acessadas a partir de GPedit. dll, que está disponível no console usuários e computadores do Active Directory e no GPMC (console de gerenciamento de política de grupo).

</div>

<div>

## <a name="group-policy-security-settings"></a>Configurações de segurança de política de grupo

A política de grupo contém configurações de segurança para um GPO em configurações do computador/configurações do Windows/configurações de segurança quando acessado a partir do GPedit. dll. Você pode importar modelos de segurança para definir configurações de segurança para o GPO. O guia de segurança do Windows Server [http://go.microsoft.com/fwlink/p/?LinkId=145186](http://go.microsoft.com/fwlink/p/?linkid=145186) 2008 em e o kit de ferramentas de gerenciamento de conformidade [http://go.microsoft.com/fwlink/p/?LinkId=211882](http://go.microsoft.com/fwlink/p/?linkid=211882) de segurança do Windows Server 2008 R2 contém vários modelos de exemplo que você pode modificar para atender às suas necessidades.

</div>

<div>

## <a name="best-practices"></a>Práticas recomendadas

  - Otimize a proteção de todos os sistemas operacionais e aplicativos do servidor.

  - Proteger os instantâneos do servidor e aprimorar a segurança de todos os servidores virtuais.

  - Use a política de grupo para implementar bloqueios de segurança.

</div>

</div>

<span> </span>

</div>

</div>

</div>

