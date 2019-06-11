---
title: Configurar o gateway do XMPP no Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: c70282e0-b502-47e2-a0be-a32eb1faf99d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721881(v=OCS.15)
ms:contentKeyID: 49733816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5609ecc72e43c28c87f9cdab1a4a7be93b89bf8f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a>Configurar o gateway do XMPP no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-10-28_

As etapas finais para migrar seu XMPP gateway são configurar certificados para o servidor de borda do Lync Server 2013, implantar o gateway do Lync Server 2013 XMPP e atualizar os registros DNS do Gateway XMPP. Essas etapas devem ser executadas em paralelo para minimizar o tempo de indisponibilidade do seu Gateway XMPP. Todos os usuários devem ser movidos para a implantação do Microsoft Lync Server 2013 antes de executar essas etapas.

<div class=" ">


> [!IMPORTANT]  
> Não há suporte para a Federação do XMPP para usuários que são hospedados em aparelhos de ramificação sobreviventes. Isso se aplica a ambos ver informações de presença e troca de mensagens INSTANTÂNEAs.



</div>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a>Configurar certificados de gateway do XMPP no servidor de borda do Lync Server 2013

1.  No servidor de borda, no assistente de implantação, ao lado da **etapa 3: solicitar, instalar ou atribuir certificados**, clique **novamente em executar**.
    
    <div class=" ">
    

    > [!TIP]  
    > Se você estiver implantando o servidor de borda pela primeira vez, você verá executar novamente em vez de executar novamente.

    
    </div>

2.  Na página **Tarefas de Certificado Disponíveis**, clique em  **Criar uma nova solicitação de certificado**.

3.  Na página **solicitação de certificado** , clique em **certificado de borda externa**.

4.  Na página **solicitação atrasada ou imediata** , marque a caixa de seleção **preparar a solicitação agora, mas enviá-la mais tarde** .

5.  Na página **arquivo de solicitação de certificado** , digite o caminho completo e o nome do arquivo para o qual a solicitação deve ser salva (por exemplo, c:\\CERT\_guia\_Edge. cer).

6.  Na página **especificar modelo de certificado alternativo** , para usar um modelo diferente do modelo padrão do webserver, marque a caixa de seleção **usar modelo de certificado alternativo para a autoridade de certificação selecionada** .

7.  Na página **configurações de nome e segurança** , faça o seguinte:
    
    1.  Em **nome amigável**, digite um nome de exibição para o certificado.
    
    2.  Em **comprimento de bit**, especifique o comprimento do bit (geralmente, o padrão de 2048).
    
    3.  Verifique se a caixa de seleção **Marcar chave privada de certificado como** exportável está marcada.

8.  Na página **informações da organização** , digite o nome da organização e da unidade organizacional (por exemplo, uma divisão ou um departamento).

9.  Na página **informações** geográficas, especifique as informações de localização.

10. Na página **nome do assunto/nomes alternativos de assunto** , as informações a serem automaticamente preenchidas pelo assistente serão exibidas. Se forem necessários nomes alternativos de entidades adicionais, especifique-os nas próximas duas etapas.

11. Na **configuração de domínio SIP na página de nomes alternativos de entidades (SANs)** , marque a caixa de seleção domínio para adicionar um SIP. \<entrada\> sipdomain para a lista de nomes alternativos de assunto.

12. Na página **configurar nomes alternativos de entidades adicionais** , especifique os nomes alternativos de entidades adicionais necessários.
    
    <div class=" ">
    

    > [!TIP]  
    > Se o proxy XMPP estiver instalado, por padrão, o nome de domínio (como contoso.com) será preenchido nas entradas de SAN. Se você precisar de mais entradas, adicione-as nesta etapa.

    
    </div>

13. Na página **Resumo da solicitação** , examine as informações do certificado a serem usadas para gerar a solicitação.

14. Após a conclusão da execução dos comandos, você pode **Exibir o log**ou clicar em avançar para continuar.

15. Na página **arquivo de solicitação de certificado** , você pode exibir o arquivo de solicitação de assinatura de certificado (CSR) gerado clicando em **Exibir** ou em sair do assistente de certificado clicando em **concluir**.

16. Copie o arquivo de solicitação e envie para sua autoridade de certificação pública.

17. Depois de receber, importar e atribuir o certificado público, você deve parar e reiniciar os serviços do servidor de borda. Para fazer isso, digite no console de gerenciamento do Lync Server:
    
        Stop-CsWindowsService

      &nbsp;
    
        Start-CsWindowsService

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a>Configurar um novo gateway do Lync Server 2013 XMPP

1.  Abra o Painel de Controle do Lync Server.

2.  Na barra de navegação à esquerda, clique em **Federação e acesso externo** e, em seguida, clique em **parceiros federados do XMPP**.

3.  Para criar uma nova configuração, clique em **novo**.

4.  Defina as seguintes configurações:

5.  **Domínio primário (**     obrigatório). O domínio primário é o domínio base do parceiro XMPP. Por exemplo, você digitaria **fabrikam.com** para o nome de domínio do parceiro XMPP. Esta é uma entrada obrigatória.

6.  **Descrição**   a descrição é para anotações ou outras informações de identificação para essa configuração específica. Esta entrada é opcional.

7.  **Domínios adicionais**   os domínios adicionais são domínios que fazem parte do domínio do seu parceiro XMPP que devem ser incluídos como parte da comunicação XMPP permitida. Por exemplo, se o domínio primário for **fabrikam.com**, você listará todos os outros domínios que estão sob fabrikam.com com os quais você irá se comunicar por meio de XMPP.

8.  **Tipo de parceiro**   o **tipo de parceiro** é uma configuração obrigatória. Você deve escolher uma das seguintes opções para descrever e reforçar quais contatos podem ser adicionados. Você pode selecionar:
    
      - **Federado**   um tipo de parceiro **federado** representa um alto nível de confiança entre a implantação do Lync Server e o parceiro XMPP.Esse tipo de parceiro é recomendado para federação com servidores XMPP na mesma empresa ou em que há uma relação comercial estabelecida.Os contatos do XMPP em parceiros federados podem:
        
        1.  Adicione contatos do Lync e visualize sua presença sem a autorização expressa do usuário do Lync.
        
        2.  Envie mensagens de chat para contatos do Lync se ou não o usuário do Lync os adicionou à lista de contatos dele.
        
        3.  Consulte as anotações de status de um usuário do Lync.
    
      - **Público verificado**   se um parceiro **verificado público** é um provedor de XMPP público confiável para verificar a identidade de seus usuários.Os contatos do XMPP em redes verificadas públicas podem adicionar contatos do Lync e exibir sua presença e enviar mensagens de chat a eles sem a autorização expressa dos usuários do Lync.Os contatos do XMPP em redes comprovadas não são exibidos nas notas de status dos usuários do Lync.Esta configuração não é recomendada.
    
      - **Não verificado**   público um parceiro não **verificado** público é um provedor de XMPP público que não é confiável para verificar a identidade de seus usuários.Os usuários do XMPP em redes públicas não verificadas não podem se comunicar com os usuários do Lync, a menos que o usuário do Lync o tenha autorizado expressamente adicionando-os à lista de contatos.Os usuários do XMPP em redes não verificadas públicas nunca podem ver as notas de status dos usuários do Lync.Essa configuração é recomendada para qualquer Federação com provedores de XMPP públicos, como o Google Talk.

9.  **Tipo de conexão:** Define as várias regras e configurações de dialback.
    
      - **A negociação**   de TLS define as regras de negociação de TLS. Um serviço XMPP pode exigir o TLS, pode criar a TLS opcional ou você define que o TLS não é compatível. Escolher opcional deixa a necessidade de até o serviço XMPP para uma decisão obrigatória a negociação. Para ver todas as configurações e os detalhes possíveis para a negociação SASL, TLS e Dialback, incluindo configurações de erro não válidas e conhecidas-consulte [configurações de negociação para XMPP parceiros federados no Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).
        
          - <span></span>  
            **Obrigatório**   o serviço XMPP exige negociação de TLS.
        
          - <span></span>  
            **Opcional**   o serviço XMPP indica que o TLS é obrigatório para negociar.
        
          - <span></span>  
            **Não compatível com**   o serviço XMPP não é compatível com TLS.
    
      - **A negociação**   SASL define as regras de negociação SASL. Um serviço XMPP pode exigir SASL, pode deixar SASL opcional, ou você define que SASL não é compatível. Escolher opcional deixa o requisito para o serviço de XMPP do parceiro para uma decisão obrigatória-para-negociação.
        
          - <span></span>  
            **Obrigatório**   o serviço XMPP requer negociação SASL.
        
          - <span></span>  
            **Opcional**   o serviço XMPP indica que a SASL é obrigatória para negociar.
        
          - <span></span>  
            **Não suportado**   o serviço XMPP não dá suporte a SASL.
    
      - **Negociação do dialback do servidor de suporte** O processo de negociação dialback do servidor de suporte usa o sistema de nomes de domínio (DNS) e um servidor autoritativo para verificar se a solicitação veio de um parceiro XMPP válido. Para fazer isso, o servidor de origem cria uma mensagem de um tipo específico com uma chave dialback gerada e procura o servidor de recebimento no DNS. O servidor de origem envia a chave em um fluxo de XML para a pesquisa de DNS resultante, supostamente o servidor de recebimento. No recebimento da chave sobre o fluxo XML, o servidor de recebimento não responde ao servidor de origem, mas envia a chave para um servidor autoritativo conhecido. O servidor autoritativo verifica se a chave é válida ou não é válida. Se não for válido, o servidor de recebimento não responderá ao servidor de origem. Se a chave for válida, o servidor de recebimento informa ao servidor de origem que a identidade e a chave são válidas e que a conversa pode começar.
        
        Há dois Estados válidos para a **negociação do Dialback**:
        
          - <span></span>  
            **True**   , o servidor XMPP está configurado para usar a negociação Dialback caso uma solicitação seja recebida de um servidor de origem.
        
          - <span></span>  
            **False**   o XMPP Server não está configurado para usar a negociação Dialback e, caso uma solicitação seja recebida de um servidor de origem, ela será ignorada.

10. Clique em **confirmar** para salvar as alterações no site ou na política de usuário.

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a>Atualizar registros DNS para o Lync Server 2013 XMPP gateway

1.  Para configurar o DNS para a Federação do XMPP, adicione o seguinte registro SRV ao seu servidor\_DNS externo: XMPP. \_TCP. \<nome\> do domínio o registro SRV será resolvido para o FQDN de borda de acesso do servidor de borda, com um valor de porta de 5269.

</div>

</div>

<span> </span>

</div>

</div>

</div>

