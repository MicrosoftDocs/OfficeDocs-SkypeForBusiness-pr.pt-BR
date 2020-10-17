---
title: 'Lync Server 2013: pré-requisitos do plug-in VDI do Lync'
description: 'Lync Server 2013: pré-requisitos do plug-in do Lync VDI.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync VDI plug-in prerequisites
ms:assetid: da25a976-7624-4dfc-b332-9c4db4ee78da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205304(v=OCS.15)
ms:contentKeyID: 48185552
ms.date: 03/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4389f776747426d07442e29418ab97e9609de7ee
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566537"
---
# <a name="lync-vdi-plug-in-prerequisites-in-lync-server-2013"></a>Pré-requisitos do plug-in VDI do Lync no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2017-03-07_

Em um ambiente de infraestrutura de área de trabalho virtual (VDI), as máquinas virtuais e o computador local do usuário devem atender aos requisitos descritos nesta seção.

<div>


> [!NOTE]  
> Consulte o provedor de solução de virtualização para obter detalhes sobre como instalar e implantar o ambiente virtualizado. Para obter informações sobre como implantar um ambiente virtualizado com base nos Serviços de Área de Trabalho Remota e Hyper-V, consulte os artigos a seguir na Biblioteca TechNet da Microsoft: 
> <UL>
> <LI>
> <P>Hyper-V em <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></P>
> <LI>
> <P>Serviços de área de trabalho remota no Windows Server &nbsp; 2008 &nbsp; R2 em <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></P></LI></UL>



</div>

A seguir estão requisitos para máquinas virtuais executando no computador do centro de dados:

  - As máquinas virtuais devem ser configuradas com Windows 10, Windows 8,1, Windows 8, Windows 7 ou Windows Server 2008 R2 com os service packs mais recentes.

Estes são os requisitos para o usuário e o computador local do usuário:

  - O usuário deve estar hospedado no Lync Server 2013.

  - O computador local deve estar executando o Windows Embedded Standard 7 com SP1, Windows 7 com SP1, Windows 8, Windows 8,1 Embedded ou Windows 8,1 (não incorporado).

  - Se você estiver usando os serviços de área de trabalho remota, a leitura de bits do plug-in VDI do Lync (ou seja, se o aplicativo for 32 bits ou 64 bits) deve corresponder ao bit de bits do sistema operacional do computador local. O bitness do sistema operacional no computador local e o sistema operacional na máquina virtual não precisam corresponder. Se você estiver usando outra solução de virtualização ou plataforma, consulte o guia do seu provedor de solução de virtualização sobre os requisitos de bitness.

  - O computador local deve estar executando a versão mais atual do cliente de área de trabalho remota. Instale as últimas atualizações do cliente dos Serviços da Área de Trabalho Remota da Microsoft ou o software do cliente de área de trabalho remota mais atual do seu provedor de solução de virtualização. Para obter as atualizações mais recentes dos serviços de área de trabalho remota, consulte [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032) .

  - No computador local, as configurações do cliente de área de trabalho remota devem ser definidas para que o áudio reproduza o computador local e a gravação remota esteja desabilitada. Para definir essas configurações para a conexão de área de trabalho remota no Windows, confira a próxima seção, "para definir as configurações da conexão de área de trabalho remota".

<div>

## <a name="to-configure-remote-desktop-connection-settings"></a>Para definir as configurações da Conexão da Área de Trabalho Remota

Para preparar a conexão de área de trabalho remota no Windows para o plug-in VDI do Lync, siga estas etapas.

1.  Se o computador local estiver executando o Windows 8, pule esta etapa. Se o computador local estiver executando o Windows 7 com SP1, instale a versão mais recente do Windows 8 do cliente de serviços de área de trabalho remota, disponível em [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032) .

2.  Inicie o cliente dos Serviços de Área de Trabalho Remota clicando em **Iniciar** e em **Conexão da Área de Trabalho Remota**.

3.  Clique em **Opções**.

4.  Clique na guia **Recursos locais**. Em **Áudio remoto**, clique em **Configurações** e faça o seguinte:
    
      - Em **Reprodução de áudio remoto**, selecione **Reproduzir neste computador**.
    
      - Em **Gravação de áudio remoto**, selecione **Não gravar**.
    
      - Clique em **OK**.

5.  Clique na guia **Experiência**. Em **Desempenho**, desmarque a caixa de seleção **Cache de bitmap persistente**.

6.  Clique na guia **Geral**. Em **Computador**, digite o nome da máquina virtual e clique em **Conectar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

