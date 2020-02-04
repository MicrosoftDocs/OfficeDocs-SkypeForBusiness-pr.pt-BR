---
title: 'Lync Server 2013: Orientações de implantação para Enterprise Voice'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Enterprise Voice
ms:assetid: 8985bd93-7613-4cef-9c89-51df6049ed9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398694(v=OCS.15)
ms:contentKeyID: 48184733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 221c09fc5dadda267baad35f4784c22cc4f3c9c6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762679"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a>Orientações de implantação para Enterprise Voice no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-21_

Este tópico descreve pré-requisitos e outras diretrizes a serem consideradas quando você estiver planejando implantar o Lync Server 2013 e a carga de trabalho do Enterprise Voice.

<div>

## <a name="deployment-prerequisites"></a>Pré-requisitos de implantação

Para obter uma experiência ideal ao implantar o Enterprise Voice, certifique-se de que sua infraestrutura de ti, rede e sistemas atenda aos seguintes pré-requisitos:

  - O Lync Server 2013 Standard Edition ou Enterprise Edition está instalado e operacional em sua rede.

  - Todos os servidores de borda são implantados e operacionais em sua rede de perímetro, incluindo servidores de borda com serviço de borda de acesso, serviço de borda A/V, serviço de borda de Webconferência e proxy reverso.

  - Um ou mais usuários foram criados e habilitados para o Lync Server.

  - O Microsoft Exchange Server 2007 Service Pack 1 (SP1) ou Service Pack mais recente ou Microsoft Exchange Server 2010 está instalado. Um deles é necessário para integrar as mensagens unificadas do Exchange (UM) ao Lync Server e para fornecer notificações ricas e informações de registro de chamadas para pontos de extremidade do cliente.

  - Um número de telefone principal exclusivo foi designado, normalizado e copiado para o atributo de **linha msRTCSIP** para cada usuário a ser habilitado para o Enterprise Voice.
    
    <div>
    

    > [!NOTE]  
    > O Lync Server suporta números e. 164 e números não direcionados para discagem interna (DID). Os números não-DID podem ser representados na <STRONG> &lt;extensão&gt; Format E&gt;. 164;&lt;ext =</STRONG> ou como uma cadeia de dígitos, com o requisito de que a extensão privada é exclusiva em toda a empresa. Por exemplo, um número privado de 1001 pode ser representado como <STRONG>+ 1425550100; ext = 1001</STRONG>ou como <STRONG>1001</STRONG>. Quando representado como <STRONG>1001</STRONG>, a expectativa é que esse número particular é exclusivo em toda a empresa.

    
    </div>

  - Os administradores que implantam o Enterprise Voice devem ser membros do grupo RTCUniversalServerAdmins.

  - No mínimo, o Office Communicator 2007 é implantado com êxito. Para usar os recursos novos para esta versão, o Lync 2013 é implantado.

  - A infraestrutura de chave gerenciada (MKI) é implantada e configurada usando uma infraestrutura de autoridade de certificação (CA) da Microsoft ou de terceiros.

  - Cada computador no qual você instalar o servidor de mediação deve ser:
    
      - Um servidor membro de um domínio e preparado para os serviços de domínio do Active Directory. Para obter os procedimentos de preparação dos serviços de domínio Active Directory, consulte [preparando os serviços de domínio Active Directory para o Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) na documentação de implantação.
    
      - Executar um dos seguintes sistemas operacionais:
        
          - <span></span>  
            A edição de 64 bits do sistema operacional padrão do Windows Server 2008
        
          - <span></span>  
            A edição de 64 bits do sistema operacional Windows Server 2008 Enterprise

  - Se a conexão com a rede telefônica pública comutada (PSTN) ou o PBX (Private Branch Exchange) for por meio de uma conexão de multiplexação de divisão por tempo (TDM), um ou mais gateways PSTN estarão disponíveis para implantação. (Se a conexão for por meio de um tronco SIP, um gateway PSTN não será necessário.)

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a>Interrupções do serviço de telefone, rede ou telefone

Se houver uma interrupção, uma interrupção ou outra degradação dos serviços de energia, rede ou telefone na sua localização, a voz, as mensagens instantâneas, a presença e outros recursos do Lync Server e qualquer dispositivo conectado ao Lync Server podem não funcionar corretamente.

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a>O Enterprise Voice depende da disponibilidade do servidor e do cliente de voz e da operabilidade de hardware

As comunicações por voz com o Lync Server dependem da disponibilidade do software do servidor e do funcionamento adequado dos clientes de voz ou dos dispositivos de hardware de hardware que se conectam ao software do servidor.

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a>Meio alternativo para acessar serviços de emergência

Para os locais em que você instala um cliente de voz (por exemplo, um computador com um cliente Lync ou um dispositivo Lync Phone Edition), recomendamos que você mantenha uma opção de backup para os usuários ligarem para serviços de emergência (por exemplo, 911 ou 999) em caso de falha de energia , degradação de conectividade de rede, interrupção do serviço de telefone ou outro problema que possa inibir a operação de dispositivos do Lync Server, Lync ou Lync Phone Edition. Essas opções alternativas podem incluir um telefone conectado a uma linha de rede telefônica comutada pública padrão ou um telefone celular.

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a>Chamadas de emergência e sistemas telefônicos de várias linhas

O uso de um sistema telefônico de várias linhas (MLTS) pode estar sujeito às leis federais ou estaduais do U. S ou das leis de outros países/regiões que exigem o MLTS fornecer o número de telefone, a extensão e/ou a localização física dos serviços de emergência aplicáveis quando um chamador é colocado nos serviços de emergência (por exemplo, ao discar um número de acesso de emergência, 999 911 como Nesta versão, o Lync Server pode ser configurado para fornecer um local físico do chamador para um provedor de serviços de emergência, conforme descrito em [planejamento para serviços de emergência (E9-1-1) no Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md). A conformidade com as leis do MLTS é a única responsabilidade do comprador do Lync Server, do cliente do Lync e dos dispositivos Lync Phone Edition.

</div>

</div>

<span> </span>

</div>

</div>

</div>

