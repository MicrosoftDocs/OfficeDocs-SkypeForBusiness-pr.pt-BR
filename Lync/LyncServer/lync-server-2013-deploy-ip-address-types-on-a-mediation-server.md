---
title: 'Lync Server 2013: Implantar tipos de endereço IP no Servidor de Mediação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Mediation Server
ms:assetid: 689ebed5-96ee-4cd4-b7ae-ee2a86a1d9b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204964(v=OCS.15)
ms:contentKeyID: 48184376
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab30a2153dc7dbf5a15557f6eeaf3b6cb65f68f7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729701"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-mediation-server-for-lync-server-2013"></a>Implantar tipos de endereço IP no Servidor de Mediação para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2016-07-28_

Usando o construtor de topologias, execute as etapas do procedimento a seguir para implantar tipos de endereços IP em um servidor de mediação.

<div>

## <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>Para implantar os tipos de endereço IP em um Servidor de Mediação

  - No construtor de topologias, em **pools de mediação**, clique com o botão direito do mouse no servidor dentro de um pool e selecione **Editar propriedades**. (Como alternativa, selecione o servidor e clique em **Editar Propriedades** no menu **Ação**.)

  - Na caixa de diálogo **Editar propriedades**, selecione o tipo de endereço IP que você deseja configurar. Para uma configuração de pilha dual, selecione **Habilitar IPv4** e **Habilitar IPv6**, como mostrado na seguinte imagem.
    
    **Caixa de diálogo Editar Propriedades para o pool de Servidores de Mediação**
    
    ![Página Propriedades gerais do Lync Server com FQDN](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Página Propriedades gerais do Lync Server com FQDN")
    
      - **Usar todos os endereços IP configurados**. Selecione esta opção se você deseja permitir qualquer endereço IP definido no computador que será usado.
        
        <div>
        

        > [!NOTE]  
        > Esta é a opção recomendada para as configurações da versão 6 do IP (IPv6).

        
        </div>
    
      - **Limitar uso de serviços para selecionar endereços IP**. Selecione esta opção para especificar um endereço específico para usar um novo servidor. Se você selecionar esta opção, é necessário inserir um valor para o Endereço IP principal.
    
      - **Endereço IP principal**. Insira um endereço IP que o servidor usará para todas as comunicações exceto a PSTN (Rede telefônica pública comutada). O endereço IP inserido deve corresponder ao formato do tipo de endereço selecionado.
    
      - **Endereço IP da PSTN**. Defina um endereço IP PSTN quando um servidor de mediação for autônomo. Este endereço deve ser compatível com o formato do tipo de endereço selecionado.
        
        <div>
        

        > [!NOTE]  
        > A instalação de placas de interface de rede (NIC) adicionais para dar suporte à configuração de endereço IP PSTN para o Lync Server 2013 não é suportada nas funções do servidor de mediação posicionado. Para obter mais informações sobre as configurações da NIC com suporte para o Lync Server 2013, consulte <A href="lync-server-2013-server-hardware-platforms.md">plataformas de hardware do servidor para o Lync server 2013</A>.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

