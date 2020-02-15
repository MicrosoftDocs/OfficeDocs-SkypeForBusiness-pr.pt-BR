---
title: 'Lync Server 2013: configurar a Unificação de mensagens no Microsoft Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Unified Messaging on Microsoft Exchange
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48183311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57e48e0ee3e7ef2b9a755ecbd64afaa0f2ce3c2e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a>Configurar a Unificação de mensagens no Microsoft Exchange para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-24_

Este tópico descreve como configurar a Unificação de mensagens (UM) do Exchange em um servidor do Microsoft Exchange para uso com o Enterprise Voice.

<div>


> [!NOTE]  
> Os exemplos de cmdlet neste tópico fornecem sintaxe para a versão do Exchange 2007 do Shell de gerenciamento do Exchange. Se você estiver executando o Exchange 2010 ou o Exchange 2013, consulte a documentação apropriada como referenciada.



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a>Para configurar um servidor que executa o UM do Exchange Server

1.  Crie um plano de discagem do protocolo SIP para cada um dos seus perfis de local do Enterprise Voice. Se você optar por usar o console de gerenciamento do Exchange, crie um novo plano de discagem com a configuração de segurança **protegida (preferencial)**.
    
    <div>
    

    > [!WARNING]  
    > Se você definir o valor de configuração de segurança como <STRONG>SIP protegido</STRONG> para exigir criptografia para o tráfego SIP, como anteriormente recomendado, observe que essa configuração de segurança em um plano de discagem é insuficiente se o pool de front-ends estiver configurado para exigir criptografia, o que significa que o pool requer criptografia para o tráfego SIP e RTP. Quando o plano de discagem e as configurações de segurança do pool não forem compatíveis, todas as chamadas para o UM do Exchange a partir do pool de front-ends falharão, resultando em um erro indicando que você tem uma "configuração de segurança incompatível".

    
    </div>
    
    Se você usar o Shell de gerenciamento do Exchange, digite:
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    Veja mais detalhes em:
    
      - Para o Office Communications Server 2007, consulte "como criar um plano de discagem URI SIP de [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632) Unificação de mensagens" em e "New- [http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666)UMDialPlan: Exchange 2007 Help" em.
    
      - Para o Exchange 2010, consulte "criar um plano de discagem [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674) de um" em e "New-UMDialplan: Exchange [http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680)2010 Help" em.
    
      - Para o Exchange 2013, consulte "unificação [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)de mensagens" em.
    
    <div>
    

    > [!NOTE]  
    > Se você selecionar um nível de segurança de <STRONG>SIPSecured</STRONG> ou <STRONG>protegido</STRONG> depende do protocolo SRTP (Secure real-time Transport Protocol) ser ativado ou desativado para criptografia de mídia. Para a integração do Lync Server 2010 com o UM do Exchange, isso deve corresponder ao nível de criptografia na configuração de mídia do Lync Server. A configuração de mídia do Lync Server pode ser exibida executando o cmdlet <STRONG>Get-CsMediaConfiguration</STRONG> . Para obter detalhes, consulte Get-CsMediaConfiguration na documentação do Shell de gerenciamento do Lync Server.<BR>Para obter detalhes sobre como selecionar a configuração de segurança VoIP apropriada, consulte <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">processo de implantação para integração de Unificação de mensagens local e Lync Server 2013</A>.

    
    </div>

2.  Execute o cmdlet a seguir para obter o FQDN (nome de domínio totalmente qualificado) para cada plano de discagem de UM:
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    Veja mais detalhes em:
    
      - Para o Exchange 2007, consulte "Get-UMDialplan: Exchange 2007 Help" [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678)em.
    
      - Para o Exchange 2010, consulte "Get-UMDialplan: Exchange 2010 Help" [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679)em.
    
      - Para o Exchange 2013, consulte "unificação [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)de mensagens" em.

3.  Registre o nome do plano de discagem de cada plano de discagem de UM. Dependendo da sua versão do Exchange Server, talvez seja necessário usar o FQDN de cada nome de plano de discagem posteriormente como o nome de cada plano de discagem do Lync Server correspondente de cada plano de discagem para que os nomes do plano de discagem coincidam.
    
    <div>
    

    > [!NOTE]  
    > Os nomes dos planos de discagem do Lync Server devem coincidir com os nomes dos planos de discagem da UM somente se o plano de discagem da UM estiver sendo executado em uma versão do Exchange <EM>anterior</EM> ao Exchange 2010

    
    </div>

4.  Adicione o plano de discagem ao servidor que está executando o UM do Exchange da seguinte maneira:
    
      - Se você optar por usar o console de gerenciamento do Exchange, poderá adicionar o plano de discagem da folha de propriedades para o servidor. Para obter instruções específicas, consulte a documentação do produto do Exchange Server.
        
        Para o Exchange 2007, consulte "como adicionar um servidor de Unificação de mensagens a [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681)um plano de discagem" em.
        
        Para o Exchange 2010, consulte "exibir ou configurar as propriedades de um servidor da UM [http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682)" em.
        
        Para o Exchange 2013, consulte "unificação [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)de mensagens" em.
    
      - Se você usar o Shell de gerenciamento do Exchange, execute o seguinte para cada um dos seus servidores de UM do Exchange:
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > Antes de executar a etapa a seguir, verifique se todos os usuários do Enterprise Voice foram configurados com uma caixa de correio do Exchange Server.<BR>Para o Exchange 2007, consulte a biblioteca do TechNet do Exchange <A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>Server 2007 no.<BR>Para o Exchange 2010, consulte a biblioteca do TechNet do Exchange <A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>Server 2010 no.<BR>Ao especificar uma política de caixa de correio para cada plano de discagem que você criou na etapa 1, selecione a política padrão ou uma que você tenha criado.

    
    </div>

5.  Navegue até \<scripts de diretório\>\\de instalação do Exchange e, se o Exchange estiver implantado em uma única floresta, digite:
    ```console
    exchucutil.ps1
    ```
    Se o Exchange estiver implantado em várias florestas, digite:
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    onde FQDN da floresta especifica a floresta na qual o Lync Server está implantado.
    
    Se você tiver um ou mais planos de discagem de UM associados a vários gateways IP, vá para a etapa 6. Se seus planos de discagem são associados a um único gateway IP, pule a etapa 6.
    
    <div>
    

    > [!IMPORTANT]  
    > Certifique-se de reiniciar o serviço de <STRONG>Front-End do Lync Server</STRONG> (rtcsrv.exe) <EM>depois</EM> de executar exchucutil.ps1. Caso contrário, o Lync Server não detectará a Unificação de mensagens na topologia.

    
    </div>

6.  Usando o Shell de gerenciamento do Exchange ou o console de gerenciamento do Exchange, desabilite a chamada de saída para todos os gateways IP associados a cada um dos planos de discagem.
    
    <div>
    

    > [!NOTE]  
    > Essa etapa é necessária para garantir que as chamadas de saída do servidor que está executando a Unificação de mensagens do Exchange Server para usuários externos (por exemplo, como é o caso dos cenários de toque no telefone) atravessam com segurança o firewall corporativo.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Ao selecionar o gateway IP da UM para permitir chamadas de saída, escolha o que é provavelmente para lidar com a maior parte do tráfego. Não permitir tráfego de saída por meio de um gateway IP que se conecta a um pool de diretores do Lync Server. Além disso, evite pools em outro site central ou em um site de filial. Você pode usar um dos seguintes métodos para bloquear chamadas de saída passando por um gateway IP:

    
    </div>
    
      - Se você usar o Shell de gerenciamento do Exchange, desabilite cada gateway IP executando o seguinte comando:
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        Para o Exchange 2007, consulte "Set-UMIPGateway: Exchange 2007 Help" [http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687)em.
        
        Para o Exchange 2010, consulte "Set-UMIPGateway: Exchange 2010 Help" [http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688)em.
    
      - Se você usar o console de gerenciamento do Exchange, desmarque a caixa de seleção **Permitir chamadas de saída por meio deste gateway IP** .
    
    <div>
    

    > [!IMPORTANT]  
    > Se o plano de discagem de URI SIP da UM estiver associado a um único gateway IP, não desautorizar chamadas de saída através desse gateway.

    
    </div>

7.  Crie um atendedor automático da UM para cada plano de discagem do Lync Server.
    
    <div>
    

    > [!IMPORTANT]  
    > Não inclua espaços no nome do atendedor automático.

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    Veja mais detalhes em:
    
      - Para o Exchange 2007, consulte "New-UMAutoAttendant: Exchange 2007 Help" [http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689)em.
    
      - Para o Exchange 2010, consulte "New-UMAutoAttendant: Exchange 2010 Help" [http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690)em.
    
    A etapa a seguir deve ser executada para cada usuário depois que você habilitar usuários do Lync Server para o Enterprise Voice e conhecer seus URIs SIP.

8.  Associar usuários de UM do Exchange (cada um deles deve ser configurado com uma caixa de correio do Exchange) com o plano de discagem de UM e criar um URI SIP para cada usuário.
    
    <div>
    

    > [!NOTE]  
    > O <STRONG>SIPResourceIdentifier</STRONG> no exemplo a seguir deve ser o endereço SIP do usuário do Lync Server.

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    Veja mais detalhes em:
    
      - Para o Exchange 2007, consulte "Enable-UMMailbox: Exchange 2007 Help" [http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691)em.
    
      - Para o Exchange 2010, consulte "Enable-UMMailbox: Exchange 2010 Help" [http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692)em.

</div>

</div>

<span> </span>

</div>

</div>

</div>

