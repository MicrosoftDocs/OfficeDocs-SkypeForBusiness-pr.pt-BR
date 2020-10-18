---
title: 'Lync Server 2013: configurar o Lync Server 2013 para trabalhar com a Unificação de mensagens no Microsoft Exchange Server'
description: 'Lync Server 2013: configurar o Lync Server 2013 para trabalhar com a Unificação de mensagens no Microsoft Exchange Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398193(v=OCS.15)
ms:contentKeyID: 48183430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05ef2902ffc03b14e04b378a2ef18e03c8c58372
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578037"
---
# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a>Configurar o Lync Server 2013 para trabalhar com a Unificação de mensagens no Microsoft Exchange Server

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

_**Última modificação do tópico:** 2013-04-03_

Esta etapa requer o Utilitário de Integração do UM do Exchange (OcsUmUtil.exe). Essa ferramenta está localizada no servidor do Lync Server 2013 no.. \\ Arquivos de programa \\ Arquivos comuns \\ do Microsoft Lync Server 2013 \\ support Folder.

<div>

## <a name="running-the-exchange-um-integration-utility"></a>Executando o Utilitário de Integração do UM do Exchange

O Utilitário de Integração do UM do Exchange deve ser executado em uma conta de usuário com as seguintes características:

  - Associação nos grupos RTCUniversalServerAdmins e RtcUniversalUserAdmins (que inclui a permissão para ler as configurações da Unificação de Mensagens do Exchange Server).

  - Direitos de usuário no domínio para criar objetos de contato no contêiner de unidade organizacional (OU) especificado.

Quando você executa o Utilitário de Integração do UM do Exchange, ele realiza as seguintes tarefas:

  - Cria objetos de contato para cada número de telefone do assinante e de atendedor automático a ser utilizado pelos usuários do Enterprise Voice.

  - Verifica se o nome de cada plano de discagem do Enterprise Voice corresponde ao seu contexto de telefone do plano de discagem de Unificação de mensagens (UM) correspondente. Essa correspondência será necessária somente se o plano de discagem da UM estiver sendo executado em uma versão do Exchange *anterior* ao Exchange 2010 Service Pack 1 (SP1).

> [!IMPORTANT]
> Antes de executar o utilitário de integração do UM do Exchange, certifique-se de ter feito o seguinte:
> <ul>
> <li><p>Crie um ou mais planos de discagem de UM do Exchange, conforme descrito na documentação do produto Exchange.</p>
> <p>Para o Microsoft Exchange Server 2010, consulte &quot; criar um plano de discagem de um &quot; em <a href="https://go.microsoft.com/fwlink/p/?linkid=186177">https://go.microsoft.com/fwlink/p/?linkId=186177</a> .</p>
> <p>Para o Microsoft Exchange Server 2007 Service Pack 1 (SP1), consulte &quot; como criar um plano de discagem URI SIP de Unificação &quot; de mensagens em <a href="https://go.microsoft.com/fwlink/p/?linkid=185771">https://go.microsoft.com/fwlink/p/?linkId=185771</a> .</p></li>
> <li><p>Crie um ou mais planos de discagem do Lync Server correspondentes, conforme descrito em <a href="lync-server-2013-create-a-dial-plan.md">Create a dial Plan in Lync server 2013</a>.</p></li>
> <ul><li>Se você estiver usando uma versão do Exchange anterior ao Microsoft Exchange Server 2010 SP1, deverá digitar o nome de domínio totalmente qualificado (FQDN) do plano de discagem SIP da Unificação de mensagens (UM) correspondente do Exchange no campo <STRONG>nome simples</STRONG> do plano de discagem do Lync Server 2013. Se você estiver usando o Microsoft Exchange Server 2010 SP1 ou o Service Pack mais recente, o nome do plano de discagem correspondente não será necessário.</li></ul>
> <li>Crie um atendedor automático e certifique-se que o número de acesso do assinante e o número do atendedor automático estejam no formato E.164.</li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a>Para executar o Utilitário de Integração do UM do Exchange

1.  Em um servidor front-end, abra um prompt de comando e digite **CD% COMMONPROGRAMFILES% \\ Microsoft Lync Server 2013 \\ support**e pressione Enter.

2.  Digite **OcsUmUtil.exe** e pressione ENTER.

3.  Clique em **Carregar Dados** para localizar todas as florestas confiáveis do Exchange.

4.  Na lista **Planos de Discagem SIP**, selecione o plano de discagem SIP do UM para o qual você deseja criar objetos de contato e clique em **Adicionar**.

5.  Na caixa **Contato**, aceite a unidade organizacional padrão ou clique em **Procurar** para iniciar o **Seletor de UO**. Na caixa **Seletor de UO**, você pode selecionar uma UO e clicar em **OK**, ou pode clicar em **Criar Nova UO** para criar uma nova unidade organizacional na raiz ou em qualquer outra UO do domínio (por exemplo, "OU=RTC Special Accounts,DC=fourthcoffee,DC=com"); em seguida, clique em **OK**.
    
    <div>
    

    > [!NOTE]  
    > O nome diferenciado (DN) da UO selecionada ou criada será agora exibido na caixa <STRONG>Unidade Organizacional</STRONG>.

    
    </div>

6.  Na caixa **Nome**, aceite o nome padrão do plano de discagem ou digite um novo nome de exibição para o objeto de contato que você está criando.
    
    <div>
    

    > [!NOTE]  
    > Por exemplo, se estiver criando um objeto de contato de acesso do assinante, bastará nomeá-lo como Acesso do Assinante.

    
    </div>

7.  Na caixa **Endereço SIP**, aceite o endereço SIP padrão ou digite um novo endereço SIP.
    
    <div>
    

    > [!NOTE]  
    > Se você digitar um novo endereço SIP, ele deve começar com <STRONG>SIP:</STRONG> (isto é, "SIP:" incluindo os dois pontos).

    
    </div>

8.  Na lista **servidor ou pool** , selecione o servidor Standard Edition ou o pool de front-ends no qual o objeto de contato deve ser habilitado.
    
    <div>
    

    > [!NOTE]  
    > De preferência, o pool selecionado deverá ser o mesmo no qual os usuários habilitados para o Enterprise Voice e o UM do Exchange estão implantados.

    
    </div>

9.  Na lista **Número de Telefone**, selecione **Insira o número de telefone** ou **Usar este número piloto do UM do Exchange** e digite um número de telefone.

10. Na lista **Tipo de Contato**, selecione o tipo de contato que deseja criar e clique em **OK**.

11. Repita as etapas de 1 a 10 para outros objetos de contato que você deseje criar.
    
    <div>
    

    > [!NOTE]  
    > Você deve criar pelo menos um contato para cada atendedor automático. Se desejar acesso externo, você também precisará de um contato Acesso do Assinante e terá que especificar números DID (discagem direta interna).

    
    </div>

</div>

Para verificar se os objetos de contato foram criados, abra Usuários e Computadores do Active Directory e selecione a UO na qual os objetos foram criados. Os objetos de contato devem aparecer no painel de detalhes.

</div>

</div>

<span> </span>

</div>

</div>

</div>

