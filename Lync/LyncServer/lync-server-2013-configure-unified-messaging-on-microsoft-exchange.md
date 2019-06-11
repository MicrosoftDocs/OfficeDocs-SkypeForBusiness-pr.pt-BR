---
title: 'Lync Server 2013: configurar a Unificação de mensagens no Microsoft Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Unified Messaging on Microsoft Exchange
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48183311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fcbdbfbca5f532b1ca192cc0e9d89e93e3c8acb1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836327"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a>Configurar a Unificação de mensagens no Microsoft Exchange para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-24_

Este tópico descreve como configurar o Microsoft Exchange Unified Messaging (um) em um servidor do Microsoft Exchange para uso com o Enterprise Voice.

<div>


> [!NOTE]  
> Os exemplos de cmdlet neste tópico fornecem a sintaxe para a versão do Exchange 2007 do Shell de gerenciamento do Exchange. Se você estiver executando o Exchange 2010 ou o Exchange 2013, consulte a documentação apropriada como referenciada.



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a>Para configurar um servidor que esteja executando o Exchange Server UM

1.  Crie um plano de discagem de URI (Uniform Resource Identifier) do UM protocolo SIP para cada um dos perfis de local de voz de sua empresa. Se você optar por usar o console de gerenciamento do Exchange, crie um novo plano de discagem com a configuração de segurança **protegida (preferencial)**.
    
    <div>
    

    > [!WARNING]  
    > Se você definir seu valor de configuração de segurança como <STRONG>SIP Secured</STRONG> para exigir criptografia somente para tráfego SIP, como recomendado anteriormente, observe que essa configuração de segurança em um plano de discagem é insuficiente se o pool de front-ends estiver configurado para exigir criptografia, o que significa o pool requer criptografia para tráfego SIP e RTP. Quando o plano de discagem e as configurações de segurança do pool não forem compatíveis, todas as chamadas para o Exchange UM do pool de front-ends falharão, resultando em um erro, indicando que você tem uma "configuração de segurança incompatível".

    
    </div>
    
    Se você usar o Shell de gerenciamento do Exchange, digite:
    
        New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    
    Para obter detalhes, consulte:
    
      - Para o Office Communications Server 2007, consulte "como criar um plano de discagem de URI SIP [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632) de Unificação de mensagens" at e "New [http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666)-UMDialPlan: Exchange 2007 ajuda" em.
    
      - Para o Exchange 2010, consulte "criar um plano de discagem [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674) de um" em e "novo-UMDialPlan: Exchange [http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680)2010 ajuda" em.
    
      - Para o Exchange 2013, consulte "mensagens unificadas" em [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).
    
    <div>
    

    > [!NOTE]  
    > Não importa se você selecionou um nível de segurança do <STRONG>SIPSecured</STRONG> ou <STRONG>protegido</STRONG> depende se o SRTP (protocolo de transporte em tempo real seguro) está ativado ou desativado para criptografia de mídia. Para a integração do Lync Server 2010 com o Exchange UM, isso deve corresponder ao nível de criptografia na configuração de mídia do Lync Server. A configuração de mídia do Lync Server pode ser exibida executando o cmdlet <STRONG>Get-CsMediaConfiguration</STRONG> . Para obter detalhes, consulte Get-CsMediaConfiguration na documentação do Shell de gerenciamento do Lync Server.<BR>Para obter detalhes sobre como selecionar a configuração de segurança de VoIP apropriada, consulte <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">processo de implantação para integrar a Unificação de mensagens local e o Lync Server 2013</A>.

    
    </div>

2.  Execute o cmdlet a seguir para obter o nome de domínio totalmente qualificado (FQDN) de cada plano de discagem do UM:
    
    ``` 
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    Para obter detalhes, consulte:
    
      - Para o Exchange 2007, consulte "Get-UMDialplan: Exchange 2007 Help" [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678)at.
    
      - Para o Exchange 2010, consulte "Get-UMDialplan: Exchange 2010 Help" [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679)at.
    
      - Para o Exchange 2013, consulte "mensagens unificadas" em [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).

3.  Grave o nome do plano de discagem de cada plano de discagem do UM. Dependendo da sua versão do Exchange Server, talvez seja necessário usar o FQDN de cada nome de plano de discagem posteriormente como o nome de cada plano de discagem do Lync Server correspondente para que os nomes dos planos de discagem sejam correspondentes.
    
    <div>
    

    > [!NOTE]  
    > Os nomes dos planos de discagem do Lync Server devem coincidir com nomes de plano de discagem do UM apenas se o plano de discagem do UM estiver sendo executado em uma versão do Exchange <EM>anterior</EM> ao Exchange 2010 SP1

    
    </div>

4.  Adicione o plano de discagem ao servidor que executa o UM do Exchange da seguinte maneira:
    
      - Se você optar por usar o console de gerenciamento do Exchange, poderá adicionar o plano de discagem na folha de propriedades do servidor. Para obter instruções específicas, consulte a documentação do produto Exchange Server.
        
        Para o Exchange 2007, consulte "como adicionar um servidor de Unificação de mensagens a [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681)um plano de discagem" em.
        
        Para o Exchange 2010, consulte "exibir ou configurar as propriedades de um servidor de um [http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682)" em.
        
        Para o Exchange 2013, consulte "mensagens unificadas" em [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).
    
      - Se você usar o Shell de gerenciamento do Exchange, execute o seguinte para cada um dos seus servidores do Exchange UM:
        
            $ums=get-umserver; 
            $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
            $ums[0].DialPlans +=$dp.Identity; 
            set-umservice -instance $ums[0]
    
    <div>
    

    > [!NOTE]  
    > Antes de executar a etapa a seguir, certifique-se de que todos os usuários do Enterprise Voice foram configurados com uma caixa de correio do Exchange Server.<BR>Para o Exchange 2007, consulte a biblioteca do TechNet do Exchange <A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>Server 2007 em.<BR>Para o Exchange 2010, consulte a biblioteca do TechNet do Exchange <A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>Server 2010 em.<BR>Ao especificar uma política de caixa de correio para cada plano de discagem que você criou na etapa 1, selecione a política padrão ou uma que você tenha criado.

    
    </div>

5.  Navegue até \<os scripts do\>\\diretório de instalação do Exchange e, se o Exchange estiver implantado em uma única floresta, digite:
    
        exchucutil.ps1
    
    Ou, se o Exchange estiver implantado em várias florestas, digite:
    
        exchucutil.ps1 -Forest:"<forest FQDN>"
    
    em que floresta FQDN especifica a floresta na qual o Lync Server é implantado.
    
    Se você tiver um ou mais planos de discagem de UM associados a vários gateways IP, vá para a etapa 6. Se seus planos de discagem estiverem associados a apenas um único gateway IP, pule a etapa 6.
    
    <div>
    

    > [!IMPORTANT]  
    > Certifique-se de reiniciar o serviço de <STRONG>front-end do Lync Server</STRONG> (RtcSrv. exe) <EM>depois</EM> de executar ExchUCUtil. ps1. Caso contrário, o Lync Server não irá detectar a Unificação de mensagens na topologia.

    
    </div>

6.  Usando o Shell de gerenciamento do Exchange ou o console de gerenciamento do Exchange, desabilite as chamadas de saída para todos, exceto um dos gateways IP associados a cada um dos planos de discagem.
    
    <div>
    

    > [!NOTE]  
    > Esta etapa é necessária para garantir que as chamadas de saída do servidor que executam a Unificação de mensagens do Exchange Server sejam feitas a usuários externos (por exemplo, se o caso com cenários de reprodução sob o telefone) atravessará com confiança o firewall corporativo.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Ao selecionar o gateway IP de UM por meio do qual permitir chamadas feitas, escolha o que você pode manipular mais o tráfego. Não permita o tráfego de saída por meio de um gateway IP que se conecta a um pool de diretores do Lync Server. Evite também pools em outro site central ou em um site de filial. Você pode usar qualquer um dos seguintes métodos para impedir que chamadas feitas passem por um gateway IP:

    
    </div>
    
      - Se você usar o Shell de gerenciamento do Exchange, desabilite cada gateway IP executando o seguinte comando:
        
            Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        
        Para o Exchange 2007, consulte "Set-UMIPGateway: Exchange 2007 Help" [http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687)at.
        
        Para o Exchange 2010, consulte "Set-UMIPGateway: Exchange 2010 Help" [http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688)at.
    
      - Se você usar o console de gerenciamento do Exchange, desmarque a caixa de seleção **Permitir chamadas de saída por meio deste gateway de IP** .
    
    <div>
    

    > [!IMPORTANT]  
    > Se o seu plano de discagem de URI SIP SIP estiver associado a um único gateway IP, não permita chamadas de saída por meio desse gateway.

    
    </div>

7.  Crie um atendedor automático da UM para cada plano de discagem do Lync Server.
    
    <div>
    

    > [!IMPORTANT]  
    > Não inclua espaços no nome do atendedor automático.

    
    </div>
    
        New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    
    Para obter detalhes, consulte:
    
      - Para o Exchange 2007, consulte "New-UMAutoAttendant: Exchange 2007 Help" [http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689)at.
    
      - Para o Exchange 2010, consulte "New-UMAutoAttendant: Exchange 2010 Help" [http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690)at.
    
    A etapa a seguir deve ser realizada para cada usuário depois que você habilitar usuários do Lync Server para Enterprise Voice e conhecer seus URIs SIP.

8.  Associe usuários do Exchange UM (cada um deve ser configurado com uma caixa Exchange mail) com o plano de discagem da UM e crie um URI SIP para cada usuário.
    
    <div>
    

    > [!NOTE]  
    > O <STRONG>SIPResourceIdentifier</STRONG> no exemplo a seguir deve ser o endereço SIP do usuário do Lync Server.

    
    </div>
    
        enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    
    Para obter detalhes, consulte:
    
      - Para o Exchange 2007, consulte "Enable-UMMailbox: Exchange 2007 Help" [http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691)at.
    
      - Para o Exchange 2010, consulte "Enable-UMMailbox: Exchange 2010 Help" [http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692)at.

</div>

</div>

<span> </span>

</div>

</div>

</div>

