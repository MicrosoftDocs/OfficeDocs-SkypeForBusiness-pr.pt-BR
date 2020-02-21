---
title: 'Lync Server 2013: definindo seus requisitos de mobilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your mobility requirements
ms:assetid: b7608335-cdeb-4aae-8e4b-d80c55f0d62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690039(v=OCS.15)
ms:contentKeyID: 48185226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2da630e422aaf7068a4252333d5221f552bce525
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-mobility-requirements-for-lync-server-2013"></a>Definindo seus requisitos de mobilidade para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-14_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Durante a fase de planejamento para o recurso de mobilidade do Lync Server 2013, quando você usa os clientes móveis do Lync 2010 Mobile e Lync 2013, toma decisões que determinam suas etapas de implantação.

Estas são as decisões que você deve considerar:

  - **Você deseja usar a descoberta automática para clientes móveis do Lync?**
    
    Se você quiser oferecer suporte à descoberta automática, precisará criar novos registros de DNS (sistema de nomes de domínio) internos e externos, adicionar nomes alternativos de entidade aos certificados nos servidores front-end, diretores e proxy reverso e modificar as regras de publicação existentes no proxy reverso. Para obter detalhes, consulte [Technical Requirements for Mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md). Com a descoberta automática, os usuários podem localizar automaticamente os serviços Web do Lync Server 2013 de qualquer lugar dentro ou fora da rede corporativa, sem inserir URLs em suas configurações de dispositivo móvel.
    
    Se você usar as configurações manuais em vez da descoberta automática, os usuários móveis precisarão inserir manualmente as seguintes URLs em seus dispositivos móveis:
    
      - https://\<ExtPoolFQDN\>/autodiscover/autodiscoverservice.svc/root para acesso externo
    
      - https://\<IntPoolFQDN\>/autodiscover/Autodiscoverservice. svc/root para acesso interno
    
    Recomendamos o uso da descoberta automática. O uso principal das configurações manuais é para solução de problemas.

  - **Se você decidir oferecer suporte à descoberta automática, estará disposto a atualizar os certificados no proxy reverso com nomes de entidade alternativos para cada domínio SIP?**
    
    Se você tiver muitos domínios SIP, a atualização de certificados públicos no proxy reverso pode se tornar muito cara. Se esse for o caso, você pode optar por implementar a descoberta automática para que a solicitação inicial de serviço de descoberta automática use HTTP na porta 80, em vez de usar HTTPS na porta 443. No entanto, essa não é a abordagem recomendada. Se você decidir escolher essa alternativa, não precisará atualizar os certificados no proxy reverso, mas precisará criar uma regra de publicação na Web para HTTP na porta 80. Para obter mais detalhes, consulte [Technical Requirements for Mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

  - **Você deseja oferecer suporte aos clientes móveis do Lync de dentro e fora da rede corporativa, ou deseja oferecer suporte somente dentro da rede corporativa?**
    
    Se você quiser oferecer suporte aos clientes móveis de dentro e fora de sua rede, os dispositivos móveis poderão acessar os recursos de mobilidade a partir de qualquer local. A configuração padrão é oferecer suporte aos clientes de dentro e fora da rede corporativa.
    
    Embora a configuração padrão permita que o tráfego do cliente móvel passe pelo site externo, é possível restringir o tráfego do cliente móvel à rede corporativa interna. Quando você restringe o tráfego para a rede interna, os usuários podem usar os aplicativos móveis do Lync em seus dispositivos móveis somente quando estão dentro da rede.
    
    Para implantações que oferecem suporte à mobilidade usando o serviço de mobilidade do MCX e o Lync 2010 Mobile, execute o cmdlet **set-CsMcxConfiguration** . Para configurar a mobilidade somente para uso interno, você usaria um comando semelhante ao seguinte:
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    <div>
    

    > [!NOTE]  
    > Não há configurações adicionais necessárias para o UCWA. UCWA não tem uma configuração somente de interno equivalente.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Se você estiver usando um servidor front-&nbsp;end do lync Server 2013 ou pools de front-ends e <STRONG>não tiver</STRONG> servidores&nbsp;front-end do Lync Server 2010 ou pools de front-ends, não <STRONG>haverá necessidade de persistência baseada em cookie</STRONG>. Se você precisar manter qualquer servidor front-end&nbsp;do lync Server 2010 ou pools de front-ends, as mesmas regras ainda serão aplicadas como no Lync Server 2010 para persistência baseada em cookie.

    
    </div>

  - **Você deseja oferecer suporte às notificações por push para dispositivos Apple iOS e Windows Phones?**
    
    Se você oferecer suporte às notificações por push, os dispositivos Apple iOS suportados e os Windows Phones receberão uma notificação sobre os eventos que ocorrem quando o aplicativo móvel está inativo. Você deve configurar seu servidor de borda para ter uma relação de Federação com o serviço de notificação por push do Lync Server baseado na nuvem, que está localizado no datacenter do Lync Online e executar um cmdlet para habilitar as notificações por push.
    
    Se você quiser dar suporte a notificações por push em sua rede Wi-Fi, além de dar suporte a notificações por push sobre as redes 3G ou de dados de provedores de dispositivos móveis, deverá abrir a porta 5223 de saída na sua rede Wi-Fi corporativa. O suporte às notificações por push sobre a rede Wi-Fi oferece suporte aos dispositivos móveis que usam apenas Wi-Fi e dispositivos móveis que possuem uma recepção interna ruim.
    
    <div>
    

    > [!IMPORTANT]  
    > A porta TCP 5223 só é necessária ao suporte a dispositivos Apple que executam o cliente móvel do Lync 2010.

    
    </div>
    
    Se você não oferecer suporte a notificações por push, os usuários de dispositivos móveis Apple e Windows phones não descobrirá sobre eventos, como convites de mensagens instantâneas ou mensagens perdidas, que ocorrem quando o aplicativo móvel está inativo.
    
    <div>
    

    > [!NOTE]  
    > Os clientes móveis do Lync 2013 em dispositivos Apple não exigem notificações por push. Os clientes móveis do Lync 2013 no Windows Phone usam notificação por push. O planejamento da notificação por push e a impressão de notificação por push permanecem os mesmos para Lync Mobile no Windows Phone e dispositivos Apple que não podem executar o cliente móvel do Lync 2013.

    
    </div>

  - **Deseja que todos os usuários tenham acesso aos recursos de mobilidade ou você deseja poder especificar quais usuários têm acesso a esses recursos?**
    
    A tabela descreve os recursos disponíveis para os usuários no Lync Server 2013. Os padrões permitem chamar via trabalho, permitir voz sobre IP (VoIP) e habilitar mobilidade. Este é o conjunto completo de opções disponíveis:
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Nome/escopo do recurso/parâmetro (os nomes de parâmetro de política podem não ser iguais)</th>
    <th>Descrição</th>
    <th>Introduzido</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Habilitar mobilidade</p>
    <p>Nome do parâmetro:<code>EnableMobility</code></p>
    <p>Escopo: global/site/usuário</p></td>
    <td><p>Configuração administrativa para controlar os usuários em um determinado escopo com o Lync Mobile instalado, se a política estiver definida como false, o usuário não poderá entrar no cliente.</p>
    <p>A configuração padrão é true.</p></td>
    <td><p>Atualização cumulativa para o Lync Server 2010: novembro de 2011</p></td>
    </tr>
    <tr class="even">
    <td><p>Habilitar voz externa</p>
    <p>Nome do parâmetro:<code>EnableOutsideVoice</code></p>
    <p>Escopo: global/site/usuário</p></td>
    <td><p>Controla a capacidade de um usuário de usar Call via Work, um recurso que permite que os usuários façam e recebam chamadas usando seus números de trabalho, em vez de seus números de celular. Se for definido como false, o usuário não poderá fazer ou receber chamadas usando seu número comercial do dispositivo móvel.</p>
    <p>A configuração padrão é true</p></td>
    <td><p>Atualização cumulativa para o Lync Server 2010: novembro de 2011</p></td>
    </tr>
    <tr class="odd">
    <td><p>Habilitar áudio e vídeo IP</p>
    <p>Nome do parâmetro:<code>EnableIPAudioVideo</code></p>
    <p>Escopo: global/site/usuário</p></td>
    <td><p>Controla se um usuário pode usar VoIP para fazer ou receber chamadas de voz ou vídeo em seus dispositivos móveis. Se for definido como false, o usuário não poderá fazer ou receber chamadas VoIP ou de vídeo em seus dispositivos.</p>
    <p>A configuração padrão é true.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="even">
    <td><p>Exigir WiFi para áudio IP</p>
    <p>Nome do parâmetro:<code>RequireWiFiForIPAudio</code></p>
    <p>Escopo: global/site/usuário</p></td>
    <td><p>Essa configuração define se o cliente será solicitado a fazer e receber chamadas por VoIP em vez da rede de dados da rede celular. Se for definido como true, o usuário poderá fazer e receber chamadas de VoIP somente quando estiver conectado a uma rede Wi-Fi.</p>
    <p>A configuração padrão é false.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="odd">
    <td><p>Exigir WiFi para vídeo IP</p>
    <p>Nome do parâmetro:<code>RequireWiFiForIPVideo</code></p>
    <p>Escopo: global/site/usuário</p></td>
    <td><p>Essa configuração define se o cliente será solicitado a fazer e receber chamadas de vídeo no Wi-Fi, em vez de na rede de dados da rede celular. Se for definido como true, o usuário poderá fazer e receber chamadas de vídeo somente quando estiver conectado a uma rede Wi-Fi.</p>
    <p>A configuração padrão é false.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    </tbody>
    </table>
    
    Para obter uma descrição das configurações de política que você pode configurar e como gerenciar as políticas, consulte [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy), [set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy), [Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy), Grant- [CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) e [Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy).

  - **Você deseja que os usuários não habilitados para Enterprise Voice possam usar o recurso Clique para ingressar a fim de entrar em conferências?**
    
    Para que os usuários tenham acesso aos recursos de mobilidade e Telefonar via Trabalho, eles precisam ser habilitados para o Enterprise Voice. No entanto, os usuários que não estão habilitados para o Enterprise Voice podem participar de conferências clicando no link em seu dispositivo móvel, caso tenham uma política de voz apropriada atribuída. Você pode atribuir uma política de voz específica a esses usuários ou certificar-se de que exista uma política global ou uma política de nível de site que se aplique a elas. A política de voz atribuída deve ter registros de uso de rede telefônica pública comutada (PSTN) e rotas que definem as áreas às quais os usuários podem discar para ingressar em uma conferência. Para obter detalhes sobre como configurar política de voz, registros de uso de PSTN e rotas, consulte [Configuring Voice Policies, PSTN Usage Records, and Voice Routes in Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).
    
    <div>
    

    > [!NOTE]  
    > Os usuários móveis que desejam usar o clique para ingressar exigem uma política de voz, junto com os registros de uso PSTN e rotas de voz relacionados, porque clicar no link no dispositivo móvel resulta em uma chamada de saída do Lync Server 2013.

    
    </div>

<div>

## <a name="see-also"></a>Confira também


[Requisitos técnicos para mobilidade no Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md)  


[Configurando políticas de voz, registros de uso de PSTN e rotas de voz no Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

