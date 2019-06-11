---
title: 'Lync Server 2013: Configurar o Lync Server 2013 para trabalhar com a Unificação de Mensagens no Microsoft Exchange Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398193(v=OCS.15)
ms:contentKeyID: 48183430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27909f4ae6231b1452cbfefdd82e0a0eb107c6fa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a>Configurar o Lync Server 2013 para trabalhar com a Unificação de Mensagens no Microsoft Exchange Server

</div>

<div id="mainSection">

<div id="mainBody">

_**Tópico da última modificação:** 2013-04-03_

Esta etapa requer o utilitário de integração do Exchange UM (OcsUmUtil. exe). Esta ferramenta está localizada no servidor do Lync Server 2013 em.. \\Arquivos de\\programas arquivos\\comuns Microsoft Lync Server\\2013 support Folder.

<div>

## <a name="running-the-exchange-um-integration-utility"></a>Executando o utilitário de integração de UM Exchange

O utilitário de integração do Exchange UM deve ser executado a partir de uma conta de usuário com as seguintes características:

  - Associação nos grupos RTCUniversalServerAdmins e RtcUniversalUserAdmins (que inclui a permissão para ler as configurações de mensagens unificadas do Exchange Server).

  - Direitos de usuário no domínio para criar objetos de contato no contêiner de unidade organizacional (OU) especificado.

Quando você executa o utilitário de integração do Exchange UM, ele executa as seguintes tarefas:

  - Cria objetos de contato para cada número de atendente e acesso do assinante a ser usado por usuários do Enterprise Voice.

  - Verifica se o nome de cada plano de discagem de voz empresarial corresponde ao seu próprio contexto de telefone de plano de discagem de mensagens unificadas (UM). Essa correspondência só será necessária se o plano de discagem do UM estiver sendo executado em uma versão do Exchange *anterior* ao Exchange 2010 Service Pack 1 (SP1).

> [!IMPORTANT]
> Antes de executar o utilitário de integração do Exchange UM, certifique-se de ter feito o seguinte:
> <ul>
> <li><p>Crie um ou mais planos de discagem de UM do Exchange, conforme descrito na documentação do produto Exchange.</p>
> <p>Para o Microsoft Exchange Server 2010, &quot;consulte criar um plano&quot; de discagem de um em. <a href="http://go.microsoft.com/fwlink/p/?linkid=186177">http://go.microsoft.com/fwlink/p/?linkId=186177</a></p>
> <p>Para Microsoft Exchange Server 2007 Service Pack 1 (SP1), consulte &quot;como criar um plano&quot; de DISCAgem de URI SIP de <a href="http://go.microsoft.com/fwlink/p/?linkid=185771">http://go.microsoft.com/fwlink/p/?linkId=185771</a>Unificação de mensagens em.</p></li>
> <li><p>Crie um ou mais planos de discagem do Lync Server correspondentes, conforme descrito em <a href="lync-server-2013-create-a-dial-plan.md">criar um plano de discagem no Lync server 2013</a>.</p></li>
> <ul><li>Se você estiver usando uma versão do Exchange anterior ao Microsoft Exchange Server 2010 SP1, deverá digitar o nome de domínio totalmente qualificado (FQDN) do plano de discagem SIP do Exchange Unified Messaging (UM) correspondente no Lync Server 2013 nome simples do plano de discagem <STRONG> </STRONG>campo. Se você estiver usando o Microsoft Exchange Server 2010 SP1 ou Service Pack mais recente, o nome do plano de discagem correspondente não será necessário.</li></ul>
> <li>Crie um atendedor automático e certifique-se de que o número de acesso do assinante e o número do auto Attendant estejam no formato E. 164.</li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a>Para executar o utilitário de integração de UM Exchange

1.  Em um servidor front-end, abra um prompt de comando e digite **CD%\\COMMONPROGRAMFILES% Microsoft Lync\\Server 2013 support**e pressione Enter.

2.  Digite **OcsUmUtil. exe**e pressione Enter.

3.  Clique em **carregar dados** para localizar todas as florestas do Exchange confiáveis.

4.  Na lista **planos de discagem SIP** , selecione um plano de discagem do um SIP para o qual você deseja criar objetos de contato e clique em **Adicionar**.

5.  Na caixa de **contato** , aceite a unidade organizacional padrão ou clique em **procurar** para iniciar o **seletor de ou**. Na caixa **seletor de ou** , você pode selecionar uma UO e clicar em **OK**, ou pode clicar em **fazer nova UO** para criar uma nova unidade organizacional na raiz ou em qualquer outra UO do domínio (por exemplo, "ou = contas especiais do RTC, DC = fourthcoffee, DC = com") e, em seguida, clique em **OK**.
    
    <div>
    

    > [!NOTE]  
    > O nome diferenciado (DN) da OU que você selecionou ou criou agora é exibido na caixa <STRONG>unidade organizacional</STRONG> .

    
    </div>

6.  Na caixa **nome** , aceite o nome do plano de discagem padrão ou digite um novo nome para exibição para o objeto de contato que você está criando.
    
    <div>
    

    > [!NOTE]  
    > Por exemplo, se você estiver criando um objeto de contato do acesso ao Assinante, você pode simplesmente nomeá-lo como assinante.

    
    </div>

7.  Na caixa **endereço SIP** , aceite o endereço SIP padrão ou digite um novo endereço SIP.
    
    <div>
    

    > [!NOTE]  
    > Se você digitar um novo endereço SIP, ele deve começar com <STRONG>SIP:</STRONG> (isto é, "SIP:" incluindo os dois-pontos).

    
    </div>

8.  Na lista **servidor ou pool** , selecione o servidor Standard Edition ou o pool de front-end no qual o objeto de contato deve ser habilitado.
    
    <div>
    

    > [!NOTE]  
    > Preferencialmente, o pool selecionado é o mesmo pool em que os usuários habilitados para o Enterprise Voice e o Exchange UM são implantados.

    
    </div>

9.  Na lista **número de telefone** , selecione **Inserir número de telefone** ou **Use este número piloto no Exchange um** e, em seguida, digite um número de telefone.

10. Na lista **tipo de contato** , selecione o tipo de contato que você deseja criar e, em seguida, clique em **OK**.

11. Repita as etapas de 1 a 10 para objetos de contato adicionais que você deseja criar.
    
    <div>
    

    > [!NOTE]  
    > Você deve criar pelo menos um contato para cada atendedor automático. Se você quiser acesso externo, também precisará de um contato do acesso do assinante e especificar números do Direct Inward Dial (DID).

    
    </div>

</div>

Para verificar se os objetos de contato foram criados, abra usuários e computadores do Active Directory e selecione a OU em que os objetos foram criados. Os objetos de contato devem aparecer no painel de detalhes.

</div>

</div>

<span> </span>

</div>

</div>

</div>

