---
title: 'Lync Server 2013: Definindo seus requisitos de mobilidade'
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
ms.openlocfilehash: 2721f88ce703fe4c26fbc7a9a6cd02cdde6b14a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-mobility-requirements-for-lync-server-2013"></a>Definindo seus requisitos de mobilidade para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-14_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Durante a fase de planejamento para o recurso de mobilidade do Lync Server 2013, quando você estiver usando clientes móveis do Lync 2010 e Lync 2013, toma decisões que determinam suas etapas de implantação.

Estas são as decisões que você deve considerar:

  - **Você deseja usar a descoberta automática para clientes móveis do Lync?**
    
    Se você quiser dar suporte à descoberta automática, será necessário criar novos registros de DNS (sistema de nome de domínio) internos e externos, adicionar nomes alternativos de entidades a certificados nos servidores de front-end, directors e proxy reverso e modificar as regras de publicação existentes no proxy reverso. Para obter detalhes, consulte [requisitos técnicos de mobilidade no Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md). Com a descoberta automática, os usuários podem localizar automaticamente os serviços Web do Lync Server 2013 de praticamente qualquer lugar dentro ou fora da rede da empresa, sem inserir URLs em suas configurações de dispositivo móvel.
    
    Se você usar as configurações manuais em vez da descoberta automática, os usuários móveis precisarão inserir manualmente as seguintes URLs em seus dispositivos móveis:
    
      - https://\<ExtPoolFQDN\>/autodiscover/autodiscoverservice.svc/root para acesso externo
    
      - https://\<IntPoolFQDN\>/autodiscover/Autodiscoverservice. svc/root para acesso interno
    
    É altamente recomendável usar a descoberta automática. O uso principal das configurações manuais é para solução de problemas.

  - **Se você decidir oferecer suporte à descoberta automática, estará disposto a atualizar certificados no proxy reverso com nomes alternativos de entidades para cada domínio SIP?**
    
    Se você tiver muitos domínios SIP, a atualização de certificados públicos no proxy reverso pode ficar muito cara. Se esse for o caso, você pode optar por implementar a descoberta automática para que a solicitação de serviço inicial de descoberta automática use HTTP na porta 80, em vez de usar HTTPS na porta 443. No entanto, essa abordagem não é recomendada. Se você decidir escolher essa alternativa, não precisará atualizar os certificados no proxy reverso, mas precisará criar uma regra de publicação na Web para HTTP na porta 80. Para obter mais detalhes, consulte [requisitos técnicos de mobilidade no Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

  - **Você deseja dar suporte a clientes móveis do Lync, internos e externos à rede corporativa, ou dar suporte a clientes somente dentro da rede corporativa?**
    
    Se você quiser dar suporte a clientes móveis internos e externos à sua rede, os dispositivos móveis poderão acessar os recursos de mobilidade de qualquer local. A configuração padrão é dar suporte a clientes internos e externos à rede corporativa.
    
    Embora a configuração padrão permita que o tráfego do cliente móvel passe pelo site externo, você pode restringir o tráfego do cliente móvel à rede corporativa interna. Quando você restringe o tráfego para a rede interna, os usuários podem usar os aplicativos móveis do Lync em seus dispositivos móveis somente quando estiverem dentro da rede.
    
    Para implantações que dão suporte à mobilidade usando o serviço de mobilidade do MCX e o Lync 2010 Mobile, execute o cmdlet **set-CsMcxConfiguration** . Para definir o Mobility somente para uso interno, você usaria um comando semelhante ao seguinte:
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    <div>
    

    > [!NOTE]  
    > Não há configurações adicionais necessárias para o UCWA. UCWA não tem uma configuração somente interna equivalente.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Se você estiver usando um servidor front-&nbsp;end do lync Server 2013 ou pools front-end e <STRONG>não tiver</STRONG> nenhum servidor&nbsp;front-end ou servidores do Lync Server 2010, não <STRONG>haverá necessidade de persistência baseada em cookies</STRONG>. Se você precisar manter todos os servidores de front&nbsp;-end do lync Server 2010 ou os pools front-end, as mesmas regras ainda serão aplicadas como no Lync Server 2010 para persistência baseada em cookies.

    
    </div>

  - **Deseja dar suporte a notificações por push para dispositivos Apple iOS e telefones Windows?**
    
    Se você dá suporte a notificações por push, dispositivos Apple iOS compatíveis e telefones Windows recebem uma notificação de eventos que ocorrem quando o aplicativo móvel está inativo. Você deve configurar seu servidor de borda para ter uma relação de Federação com o serviço de notificação por push do Lync Server baseado na nuvem, localizado no datacenter do Lync Online e executar um cmdlet para habilitar as notificações por push.
    
    Se você quiser dar suporte a notificações por push em sua rede Wi-Fi, além de oferecer suporte a notificações por push em redes 3G ou redes de provedores de dispositivos móveis, você deve abrir a porta 5223 de saída na rede Wi-Fi da empresa. Dar suporte a notificações por push pela rede Wi-Fi suporta dispositivos móveis que usam apenas Wi-Fi e dispositivos móveis com recepção interna deficiente.
    
    <div>
    

    > [!IMPORTANT]  
    > A portabilidade TCP 5223 é necessária apenas ao oferecer suporte a dispositivos Apple que executam o cliente móvel Lync 2010.

    
    </div>
    
    Se você não oferecer suporte a notificações por push, os usuários de dispositivos móveis da Apple e telefones Windows não descobrirão sobre eventos, como convites de mensagem instantânea ou mensagens perdidas, que ocorrem quando o aplicativo móvel está inativo.
    
    <div>
    

    > [!NOTE]  
    > Os clientes móveis do Lync 2013 em dispositivos Apple não exigem notificações por push. Os clientes móveis do Lync 2013 no Windows Phone usam notificações por push. Planejar a notificação por push e a Clearinghouse de notificação por push permanecerá o mesmo para o Lync Mobile em dispositivos Windows Phone e Apple que não sejam capazes de executar o cliente móvel do Lync 2013.

    
    </div>

  - **Deseja que todos os usuários tenham acesso aos recursos de mobilidade ou que você queira poder especificar quais usuários têm acesso a esses recursos?**
    
    A tabela descreve os recursos disponíveis para os usuários no Lync Server 2013. Os padrões permitem ligar por meio do trabalho, permitir voz sobre IP (VoIP) e habilitar a mobilidade. Aqui está o conjunto completo de opções disponíveis:
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Nome/escopo do recurso/parâmetro (nomes de parâmetro de política podem não ser iguais)</th>
    <th>Descrição</th>
    <th>Incluídos</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Habilitar mobilidade</p>
    <p>Nome do parâmetro:<code>EnableMobility</code></p>
    <p>Scope: global/site/usuário</p></td>
    <td><p>Configuração administrativa para controlar os usuários em um determinado escopo que tenham o Lync Mobile instalado, se a política estiver definida como false, o usuário não poderá entrar no cliente.</p>
    <p>A configuração padrão é true.</p></td>
    <td><p>Atualização cumulativa do Lync Server 2010: novembro de 2011</p></td>
    </tr>
    <tr class="even">
    <td><p>Habilitar voz externa</p>
    <p>Nome do parâmetro:<code>EnableOutsideVoice</code></p>
    <p>Scope: global/site/usuário</p></td>
    <td><p>Controla a capacidade de um usuário de usar a chamada via trabalho, um recurso que permite aos usuários fazer e receber chamadas usando o número do trabalho dele em vez do número do celular. Se definido como false, o usuário não poderá fazer ou receber chamadas usando o seu número comercial do seu dispositivo móvel.</p>
    <p>A configuração padrão é true</p></td>
    <td><p>Atualização cumulativa do Lync Server 2010: novembro de 2011</p></td>
    </tr>
    <tr class="odd">
    <td><p>Habilitar áudio e vídeo por IP</p>
    <p>Nome do parâmetro:<code>EnableIPAudioVideo</code></p>
    <p>Scope: global/site/usuário</p></td>
    <td><p>Controla se um usuário pode usar o VoIP para fazer ou receber chamadas de voz ou com vídeo em seus dispositivos móveis. Se definido como false, o usuário não poderá fazer nem receber chamadas de vídeo ou de VoIP em seus dispositivos.</p>
    <p>A configuração padrão é true.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="even">
    <td><p>Requer WiFi para áudio por IP</p>
    <p>Nome do parâmetro:<code>RequireWiFiForIPAudio</code></p>
    <p>Scope: global/site/usuário</p></td>
    <td><p>Essa configuração define se o cliente será obrigado a fazer e receber chamadas por VoIP em WiFi em vez da rede de dados da rede celular. Se definido como true, o usuário poderá fazer e receber chamadas de VoIP somente quando estiver conectado a uma rede WiFi.</p>
    <p>A configuração padrão é false.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="odd">
    <td><p>Requer WiFi para vídeo por IP</p>
    <p>Nome do parâmetro:<code>RequireWiFiForIPVideo</code></p>
    <p>Scope: global/site/usuário</p></td>
    <td><p>Essa configuração define se o cliente será obrigado a fazer e receber chamadas com vídeo em Wi-Fi, em vez de na rede de dados da rede celular. Se definido como true, o usuário poderá fazer e receber chamadas com vídeo somente quando estiver conectado a uma rede Wi-Fi.</p>
    <p>A configuração padrão é false.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    </tbody>
    </table>
    
    Para obter uma descrição das configurações de política que você pode configurar e como gerenciar as políticas, consulte [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy), [set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy), [Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy), [Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) e [Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy).

  - **Você deseja que os usuários que não estão habilitados para o Enterprise Voice possam usar o clique para ingressar em conferências?**
    
    Para que os usuários tenham acesso aos recursos da mobilidade e liguem pelo trabalho, eles devem ser habilitados para o Enterprise Voice. No entanto, os usuários que não estão habilitados para o Enterprise Voice podem participar de conferências clicando no link em seu dispositivo móvel, caso tenham uma política de voz apropriada atribuída a eles. Você pode atribuir uma política de voz específica a esses usuários ou verificar se existe uma política global ou política de nível de site que se aplica a ele. A política de voz que você atribui deve ter registros de uso de rede telefônica pública comutada (PSTN) e rotas que definem as áreas às quais os usuários podem discar para ingressar em uma conferência. Para obter detalhes sobre a configuração de política de voz, registros de uso de PSTN e rotas, consulte [Configurando políticas de voz, registros de uso PSTN e rotas de voz no Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).
    
    <div>
    

    > [!NOTE]  
    > Os usuários móveis que desejam usar o clique para ingressar exigem uma política de voz, juntamente com os registros de uso PSTN e rotas de voz relacionados, porque clicar no link no dispositivo móvel resulta em uma chamada de saída do Lync Server 2013.

    
    </div>

<div>

## <a name="see-also"></a>Confira também


[Requisitos técnicos para mobilidade no Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md)  


[Configurar políticas de voz, registros de uso de PSTN e rotas de voz no Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

