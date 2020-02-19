---
title: Configurar o Gateway XMPP no Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: 00777a34-cc36-4992-9459-08c14543ef6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687953(v=OCS.15)
ms:contentKeyID: 49733538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e1b9134b1dd1c22fed888d409dd9ea21c9877ee
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a>Configurar o Gateway XMPP no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-19_

Ao configurar políticas para suportar parceiros federados XMPP, as políticas para usuários dos domínios federados XMPP, mas não usuários de provedores de serviço de mensagem instantânea (IM) do SIP (por exemplo, Windows Live) ou domínios federados SIP. Você configura um Parceiro Federado XMPP para cada domínio federado XMPP que você deseja permitir seus usuários para adicionar contatos e comunicar-se com eles. Depois que as políticas estiverem em vigor, as tarefas adicionais incluirão a configuração dos certificados de gateway do XMPP, a implantação do Gateway XMPP do Lync Server 2013 e, finalmente, a atualização dos registros DNS do Gateway XMPP.

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a>Configurar certificados do Gateway XMPP no Servidor de Borda do Lync Server 2013

1.  No Servidor de Borda, no Assistente de Implantação, próximo a **Etapa 3: Solicitar, instalar ou atribuir certificados**, clique em **Executar novamente**.
    
    <div class=" ">
    

    > [!TIP]  
    > Se estiver implantando o Servidor de Borda pela primeira vez, você verá Executar ao invés de Executar novamente.

    
    </div>

2.  Na página **Tarefas de Certificado Disponíveis**, clique em **Criar uma nova solicitação de certificado**.

3.  Na página **Solicitação de Certificado**, clique em **Certificado de Borda Externa**.

4.  Na página **Solicitação Atrasada ou Imediata**, marque a caixa de seleção **Preparar a solicitação agora, mas enviá-la depois**.

5.  Na página **arquivo de solicitação de certificado** , digite o caminho completo e o nome do arquivo para o qual a solicitação será salva (por exemplo, c:\\CERT\_externos\_Edge. cer).

6.  Na página **Especificar Modelo de Certificado Alternativo**, para usar um modelo diferente do modelo WebServer padrão, marque a caixa de seleção **Usar o modelo de certificado alternativo para a autoridade de certificação selecionada**.

7.  Na página **Nome e Configurações de Segurança**, siga estes procedimentos:
    
    1.  Em **Nome amigável**, digite um nome para exibição do certificado.
    
    2.  Em **Comprimento de bit**, especifique o comprimento de bit (normalmente o padrão de 2048).
    
    3.  Verifique se a caixa de seleção **Marcar chave privada de certificado como exportável**  está marcada.

8.  Na página **Informações da Organização**, digite o nome da organização e a unidade organizacional (por exemplo, uma divisão ou departamento).

9.  Na página **Informações Geográficas**, especifique as informações de localização.

10. Na página **Nome da Entidade/Nomes Alternativos da Entidade**, as informações a serem preenchidas automaticamente pelo assistente são exibidas. Se nomes alternativos de entidade adicionais forem necessários, especifique-os nas próximas duas etapas.

11. Na página **configuração do domínio SIP em nomes alternativos da entidade (SANs)** , marque a caixa de seleção domínio para adicionar um SIP. \<entrada\> sipdomain para a lista de nomes alternativos de entidade.

12. Na página **Configurar Nomes Alternativos da Entidade Adicionais**, especifique quaisquer nomes alternativos de entidade adicionais que sejam necessários.
    
    <div class=" ">
    

    > [!TIP]  
    > Se o proxy XMPP é instalado, por padrão o nome de domínio (como contoso.com) é preenchido nas entradas SAN. Se você precisa de mais entradas, adicione-as nesta etapa.

    
    </div>

13. Na página **Resumo da Solicitação**, revise as informações do certificado a serem usadas para gerar a solicitação.

14. Após a conclusão da execução dos comandos, é possível **Exibir o Log** ou clicar em **Avançar** para continuar.

15. Na página **Arquivo de Solicitação de Certificado**, veja o arquivo de solicitação de assinatura de certificado (CSR) gerado clicando em Exibir ou saia do Assistente de Certificado clicando em **Concluir**.

16. Copie o arquivo de solicitação e envie-o à sua autoridade de certificação pública.

17. Após receber, importar e atribuir o certificado público, você deve parar e reiniciar os serviços do Servidor de Borda. Você faz isso digitando no console do Gerenciamento do Lync Server:
    
       ```console
        Stop-CsWindowsService
       ```
    
       ```console
        Start-CsWindowsService
       ```

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a>Configurar um novo Gateway XMPP do Lync Server 2013

1.  Abra o Painel de Controle do Lync Server.

2.  Na barra de navegação esquerda, clique em **Acesso Externo e Federação** e em **Parceiros XMPP Federados**.

3.  Para criar uma nova configuração, clique em **Novo**.

4.  Defina as configurações globais:

5.  **Domínio primário (**     obrigatório). O domínio primário é o domínio base do parceiro XMPP. Por exemplo, você deveria inserir **fabrikam.com** para o nome de domínio do parceiro XMPP. Esta é uma entrada necessária.

6.  **Descrição**   a descrição é para anotações ou outras informações de identificação para esta configuração específica. Esta entrada é opcional.

7.  **Domínios adicionais domínios**   adicionais são domínios que fazem parte do domínio do seu parceiro do XMPP que devem ser incluídos como parte da comunicação do XMPP permitido. Por exemplo, se o domínio primário é **fabrikam.com**, você deve listar todos os outros domínios sob fabrikam.com que irão se comunicar através do XMPP.

8.  **Tipo de parceiro**   o **tipo de parceiro** é uma configuração obrigatória. Você deve escolher um dos seguintes para descrever e forçar quais contatos podem ser adicionados. É possível selecionar entre:
    
      - **Federado** Um tipo de parceiro **federado** representa um alto nível de confiança entre a implantação do Lync Server e o parceiro XMPP.Este tipo de parceiro é recomendado para federação com servidores XMPP dentro da mesma empresa ou se há uma relação comercial estabelecida.Os contatos XMPP nos parceiros Federados podem:
        
        1.  Adicionar contatos do Lync e exibir sua presença sem autorização expressa do usuário Lync.
        
        2.  Enviar mensagens instantâneas para contatos do Lync se o usuário do Lync os adicionou ou não em sua lista de contatos.
        
        3.  Veja as notas de status do usuário do Lync.
    
      - **Público verificado** um parceiro **público verificado** é um provedor de XMPP público que é confiável para verificar a identidade de seus usuários.Os contatos XMPP nas redes Públicas verificadas podem adicionar contatos do Lync e exibir sua presença e enviar mensagens instantâneas para eles sem expressar a autorização dos usuários do Lync.Os contatos do XMPP em redes verificadas públicas nunca veem as notas de status dos usuários do Lync.Essa configuração não é recomendada.
    
      - **Público não verificado** Um parceiro **Público não verificado** é um provedor XMPP público não confiável para verificar a identidade de seus usuários.  Usuários XMPP em redes Públicas não verificadas não podem se comunicar com usuários do Lync, a menos que o usuário do Lync os autorize expressamente adicionando-os à lista de contatos.  Os usuários XMPP em redes públicas não verificadas nunca veem as notas de status de usuários do Lync.  Essa configuração é recomendada para qualquer federação com provedores XMPP públicos como o Google Talk.

9.  **Tipo de conexão:** define as diversas regras e configurações de retorno de chamada.
    
      - **A negociação**   TLS define as regras de negociação TLS. Um serviço XMPP pode exigir TLS, pode tornar o TLS opcional, ou definir que o TLS não é suportado. Escolher Opcional deixa os requisitos para o serviço XMPP para uma decisão de obrigatória para negociação. Para exibir todas as configurações e detalhes possíveis para a negociação SASL, TLS e Dialback – incluindo configurações de erro não válidas e conhecidas-consulte [configurações de negociação para parceiros federados do XMPP no Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)
        
           - **Obrigatório**   o serviço XMPP requer negociação TLS.
        
           - **Opcional**   o serviço XMPP indica que o TLS é obrigatório para negociar.
        
           - **Não suportado**   o serviço XMPP não oferece suporte a TLS.
    
      - **A negociação**   SASL define as regras de negociação SASL. Um serviço XMPP pode exigir SASL, pode tornar SASL opcional ou definir que o SASL não é suportado. Escolher Opcional deixa os requisitos para o serviço XMPP parceiro para uma decisão de obrigatório para negociar.
        
           - **Obrigatório**   o serviço XMPP requer negociação SASL.
        
           - **Opcional**   o serviço XMPP indica que SASL é obrigatório para negociar.
        
           - **Não suportado**   o serviço XMPP não suporta SASL.
    
      - **Dialback negociação de servidor de suporte** O processo de negociação dialback do servidor de suporte usa o DNS (sistema de nomes de domínio) e um servidor autoritativo para verificar se a solicitação provém de um parceiro do XMPP válido. Para fazer isso, o servidor originador cria uma mensagem de um tipo específico com uma chave de discagem gerada e procura o servidor de recebimento no DNS. O servidor originador envia a chave em um fluxo XML para a pesquisa DNS resultante, provavelmente o servidor recebedor. Na receita do fluxo chave sobre XML, o servidor recebedor não responde ao servidor originador, mas envia a chave para um servidor autoritativo conhecido. O servidor autoritativo verifica se a chave é válida ou inválida. Se não for válida, o servidor recebedor não responde ao servidor originador. Se a chave é válida, o servidor recebedor informa ao servidor originador que a identidade e a chave é válida e a conversação pode começar.
        
        Existem dois estados válidos para **Negociação de discagem**:
        
           - **True**   o servidor do XMPP está configurado para usar a negociação do Dialback se uma solicitação precisar ser recebida de um servidor de origem.
        
           - **False**   o servidor XMPP não está configurado para usar a negociação Dialback e, se uma solicitação for recebida de um servidor de origem, ela será ignorada.

10. Clique em **Confirmar** para salvar suas mudanças para a política local ou do usuário.

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a>Atualizar registros DNS para Gateway XMPP do Lync Server 2013

1.  Para configurar o DNS para Federação XMPP, adicione o seguinte registro SRV ao seu DNS externo:\_XMPP-Server. \_TCP. \<nome\> do domínio o registro SRV resolverá o FQDN de borda de acesso do servidor de borda, com um valor de porta de 5269.

</div>

</div>

<span> </span>

</div>

</div>

</div>

