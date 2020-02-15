---
title: 'Lync Server 2013: diretrizes de implantação para o Enterprise Voice'
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
ms.openlocfilehash: 770dfe3ce43af7dc2e6984698c095430b5c34f69
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a>Diretrizes de implantação para o Enterprise Voice no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

Este tópico descreve os pré-requisitos e outras diretrizes a serem consideradas ao planejar a implantação do Lync Server 2013 e da carga de trabalho do Enterprise Voice.

<div>

## <a name="deployment-prerequisites"></a>Pré-requisitos de implantação

Para obter uma experiência ideal ao implantar o Enterprise Voice, verifique se a infraestrutura de ti, a rede e os sistemas atendem aos seguintes pré-requisitos:

  - O Lync Server 2013 Standard Edition ou Enterprise Edition está instalado e operacional em sua rede.

  - Todos os servidores de borda são implantados e operados em sua rede de perímetro, incluindo servidores de borda com serviço de borda de acesso, serviço de borda de A/V, serviço de borda de Webconferência e um proxy reverso.

  - Um ou mais usuários foram criados e habilitados para o Lync Server.

  - O Microsoft Exchange Server 2007 Service Pack 1 (SP1) ou o Service Pack mais recente ou o Microsoft Exchange Server 2010 está instalado. Um deles é necessário para integrar a Unificação de mensagens (UM) do Exchange com o Lync Server e fornecer notificações ricas e informações de log de chamadas para pontos de extremidade do cliente.

  - Um número de telefone principal exclusivo foi designado, normalizado e copiado para o atributo **msRTCSIP-line** para cada usuário que deve ser habilitado para o Enterprise Voice.
    
    <div>
    

    > [!NOTE]  
    > O Lync Server suporta números e. 164 e números DID (discagem não direta interna). Números não-DID podem ser representados no formato <STRONG> &lt;E. 164&gt;; ext =&lt;Extension&gt; </STRONG> ou como uma cadeia de caracteres de dígitos, com o requisito de que a extensão privada é exclusiva em toda a empresa. Por exemplo, um número particular de 1001 pode ser representado como <STRONG>+1425550100;ext=1001</STRONG>, ou como <STRONG>1001</STRONG>. Quando representado como <STRONG>1001</STRONG>, a expectativa é de que esse número particular seja exclusivo na empresa.

    
    </div>

  - Os administradores que implantam o Enterprise Voice devem ser membros do grupo RTCUniversalServerAdmins.

  - No mínimo, o Office Communicator 2007 é implantado com êxito. Para usar os recursos novos para esta versão, o Lync 2013 é implantado.

  - A Infraestrutura de chave gerenciada (MKI) é implantada e configurada usando uma infraestrutura da autoridade de certificação (CA) de terceiros ou da Microsoft.

  - Cada computador no qual o Servidor de Mediação será instalado deve ser:
    
      - Um servidor membro de um domínio e preparado para os serviços de domínio do Active Directory. Para obter os procedimentos de preparação dos serviços de domínio do Active Directory, consulte [preparação dos serviços de domínio do Active Directory para o Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) na documentação de implantação.
    
      - Executando um dos seguintes sistemas operacionais:
        
          - <span></span>  
            A edição de 64 bits do sistema operacional Windows Server 2008 Standard
        
          - <span></span>  
            A edição de 64 bits do sistema operacional Windows Server 2008 Enterprise

  - Se a conexão ao PBX ou PSTN ocorrer por meio de uma conexão de TDM (multiplexação de divisão de tempo), um ou mais gateways PSTN estarão disponíveis para implantação. Se a conexão ocorrer por meio de um tronco SIP, não é necessário ter um gateway PSTN.

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a>Interrupções de energia, da rede ou dos serviços telefônicos

Se houver uma interrupção, interrupção ou outra degradação dos serviços de energia, rede ou telefone no seu local, a voz, as mensagens instantâneas, a presença e outros recursos do Lync Server e qualquer dispositivo conectado ao Lync Server poderão não funcionar corretamente.

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a>O Enterprise Voice depende da disponibilidade do servidor e da operabilidade do hardware e do cliente VoIP

As comunicações de voz com o Lync Server dependem da disponibilidade do software do servidor e do funcionamento correto dos clientes de voz ou dos dispositivos de telefone de hardware que se conectam ao software do servidor.

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a>Meios alternativos de acessar serviços de emergência

Para os locais onde você instala um cliente de voz (por exemplo, um computador que executa o Lync Client ou um dispositivo do Lync Phone Edition), recomendamos que você mantenha uma opção de backup para que os usuários liguem para os serviços de emergência (por exemplo, 911 ou 999) em caso de falha de energia , degradação da conectividade de rede, interrupção do serviço de telefone ou outro problema que pode inibir a operação de dispositivos do Lync Server, Lync ou Lync Phone Edition. Tais opções alternativas poderiam incluir um telefone conectado a uma linha de PSTNpadrão ou um telefone celular.

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a>Chamadas de emergência e sistemas telefônicos de várias linhas

O uso de um sistema telefônico de várias linhas (MLTS) pode estar sujeito às leis federais dos EUA ou às leis de outros países/regiões que requerem que o sistema MLTS forneça o número de telefone do chamador, a extensão e/ou o local físico para os serviços de emergência aplicáveis quando um chamador chama serviços de emergência (por exemplo, ao discar um número de acesso de emergência, como 901). Nesta versão, o Lync Server pode ser configurado para fornecer o local físico de um chamador para um provedor de serviços de emergência, conforme descrito em [Planning for Emergency Services (E9-1-1) no Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md). A conformidade com as leis do MLTS é a única responsabilidade do comprador de dispositivos do Lync Server, Lync Client e Lync Phone Edition.

</div>

</div>

<span> </span>

</div>

</div>

</div>

