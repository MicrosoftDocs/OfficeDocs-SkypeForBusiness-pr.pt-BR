---
title: 'Lync Server 2013: preparando e instalando o analisador de práticas recomendadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing for and installing Best Practices Analyzer
ms:assetid: 550613dd-dc08-482e-9980-a3fe187cd162
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591347(v=OCS.15)
ms:contentKeyID: 48184149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f5992b45d8930bac880f66422d10ddbd4b94f18
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747411"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a>Preparando e instalando o analisador de práticas recomendadas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-11-07_

Você deve estar conectado como um membro do grupo Administradores para executar as tarefas descritas neste tópico.

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a>Requisitos do sistema para a instalação do analisador de práticas recomendadas

Para executar o Lync Server 2013, o analisador de práticas recomendadas para verificar seu ambiente, o computador deve estar executando uma edição de 64 bits de um dos seguintes sistemas operacionais:

  - Sistema operacional padrão do Windows Server 2008 R2 com Service Pack 1 (SP1)

  - Sistema operacional Windows Server 2008 R2 com SP1 Enterprise

  - Sistema operacional de datacenter do Windows Server 2008 R2 com SP1

  - Sistema operacional Windows Server 2012 datacenter

  - Sistema operacional padrão do Windows Server 2012

  - Sistema operacional Windows Server 2012 Enterprise

  - Sistema operacional Windows Server 2012 R2 Datacenter

  - Sistema operacional padrão do Windows Server 2012 R2

  - Sistema operacional Windows Server 2012 R2 Enterprise

  - Sistema operacional Windows 8

  - Sistema operacional Windows 7

O computador também deve estar executando o seguinte:

  - Microsoft .NET Framework 4,5. Para o Lync Server 2013, você deve instalar manualmente a edição de 64 bits do Microsoft .NET Framework 4,5 no servidor antes de instalar o Lync Server 2013.

  - Lync Server 2013, componentes principais.

  - Pacote de compatibilidade com versões anteriores do WMI. Para obter detalhes, consulte [instalar o pacote de compatibilidade com versões anteriores do WMI](install-wmi-backward-compatibility-package.md) na documentação de migração.

  - Windows PowerShell 3,0. Para obter detalhes, consulte [instalando o Windows PowerShell 3,0 para Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) na documentação de implantação.

Você pode instalar o analisador de práticas recomendadas em computadores com um sistema operacional com suporte que não esteja executando o Lync Server 2013, componentes principais ou pacote de compatibilidade com versões anteriores do WMI, mas você pode usar o analisador de práticas recomendadas apenas nesses computadores para ver relatórios e não para executar verificações.

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a>Escolher um computador para instalação

Recomendamos que você instale o Lync Server 2013, o analisador de práticas recomendadas em um computador dedicado ao gerenciamento do Lync Server 2013. Você pode instalar a ferramenta em um servidor que executa o Lync Server 2013 ou um computador administrativo executando o Lync Server 2013 ferramentas administrativas. Se você instalar a ferramenta em um servidor que está executando o Lync Server, recomendamos usar a ferramenta para verificar somente esse servidor.

</div>

<div>

## <a name="installing-best-practices-analyzer"></a>Instalando o analisador de práticas recomendadas

Você pode baixar o analisador de práticas recomendadas para o [http://go.microsoft.com/fwlink/p/?linkId=266539](http://go.microsoft.com/fwlink/p/?linkid=266539)Lync Server 2013 em.

Para instalar o analisador de práticas recomendadas, inicie o arquivo Microsoft Installer RtcBPA. msi no computador onde você deseja instalar a ferramenta e siga as instruções na tela. O local padrão para a instalação dos arquivos de \<programa é\>\\arquivos\\de programa da unidade\\do sistema, Lync Server 2013 BPA.

</div>

</div>

<span> </span>

</div>

</div>

</div>

