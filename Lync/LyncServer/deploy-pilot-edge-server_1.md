---
title: Implantar um Servidor de Borda piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9cfe98069d3c90f4e021b34f6a7d31c583e7565
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a>Implantar um Servidor de Borda piloto

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-19_

Este tópico destaca as configurações de configuração das quais você deve estar ciente antes de implantar seu servidor de borda do Lync Server 2013. Esta seção destaca apenas os pontos-chave que você deve considerar como parte da sua implantação do pool de bordas piloto. Para obter etapas detalhadas, consulte Implantando o [acesso de usuários externos no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) na documentação de implantação, que descreve o processo de implantação e também fornece informações de configuração para o acesso de usuários externos.

Ao navegar pelo assistente **definir novo pool de borda** , examine as configurações de chave de configuração mostradas nas etapas a seguir. Observe que apenas algumas páginas do assistente para **definir novo pool de borda** são mostradas.

**Definir um pool de bordas**

1.  Abra a topologia do pool piloto usando o construtor de topologias.

2.  Navegue até o nó do Lync Server 2013. Clique com o botão direito do mouse em **conjuntos de bordas**e clique em **novo pool de bordas**.
    
    ![Definir a caixa de diálogo novo pool de bordas] (images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Definir a caixa de diálogo novo pool de bordas")

3.  Um pool de bordas pode ser um **pool de vários computadores** ou um **único pool de computadores**.
    
    ![Definir a caixa de diálogo FQDN do pool de bordas] (images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Definir a caixa de diálogo FQDN do pool de bordas")

4.  Na página **selecionar recursos** , não habilite Federação ou Federação do XMPP. Atualmente, a Federação e a Federação do XMPP são roteadas por meio do servidor de borda herdado do Office Communications Server 2007 R2. Esses recursos serão configurados em uma fase posterior da migração.
    
    ![Caixa de diálogo Selecionar recursos] (images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Caixa de diálogo Selecionar recursos")

5.  Em seguida, continue a concluir as seguintes páginas do assistente: **selecione opções de IP**, **FQDNs externos**, **defina o endereço IP interno**e **defina o endereço IP externo**.

6.  Na página **definir o próximo salto** , selecione o diretor do próximo nó do pool de bordas do Lync Server 2013.
    
    ![Caixa de diálogo Definir novo pool de borda, próxima lista de pools de saltos] (images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Caixa de diálogo Definir novo pool de borda, próxima lista de pools de saltos")

7.  Na página **associar pools de front-end** , não associe um pool a este pool de bordas no momento. O tráfego de mídia externo está atualmente roteado por meio do servidor de borda do Office Communications Server 2007 R2 herdado. Essa configuração será configurada em uma fase posterior da migração.
    
    ![Caixa de diálogo Definir novo pool de bordas] (images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Caixa de diálogo Definir novo pool de bordas")

8.  Clique em **concluir** e **publique** a topologia.

9.  Siga as etapas em [instalar servidores de borda para o Lync server 2013](lync-server-2013-install-edge-servers.md) na documentação de implantação para instalar os arquivos no novo servidor de borda, configurar certificados e iniciar os serviços.

É muito importante que você siga as diretrizes nos tópicos implantando o [acesso de usuários externos no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) na documentação de implantação. Esta seção simplesmente forneceu algumas diretrizes sobre as definições de configuração durante a instalação dessas funções de servidor.

Agora você deve ter uma implantação herdada do servidor de borda do Office Communications Server 2007 R2, indicada pela presença do BackCompatSite, em paralelo com uma implantação do servidor de borda 2013 do Lync Server. A Federação está configurada para usar o diretor do Office Communications Server 2007 R2. Verifique se as duas implantações estão funcionando corretamente, se os serviços foram iniciados e você pode administrar cada implantação antes de passar para a próxima fase.

![Construtor de topologias mostrando o servidor de borda do OCS] (images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Construtor de topologias mostrando o servidor de borda do OCS")

</div>

<span> </span>

</div>

</div>

</div>

