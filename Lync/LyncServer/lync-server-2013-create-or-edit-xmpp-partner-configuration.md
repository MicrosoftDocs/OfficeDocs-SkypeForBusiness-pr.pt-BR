---
title: 'Lync Server 2013: Criar ou editar configuração do parceiro XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or edit XMPP partner configuration
ms:assetid: 362dbe5e-8ee9-4aba-8c26-5907312b4a60
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552447(v=OCS.15)
ms:contentKeyID: 48679558
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 488fa84a3f24133c6ebcde4467cacdbdcffe7ff8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-xmpp-partner-configuration-in-lync-server-2013"></a>Criar ou editar configuração do parceiro XMPP no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-09-03_

O Microsoft Lync Server 2013 integra um proxy Extensible Messaging and Presence Protocol (XMPP) no servidor de borda e um Gateway XMPP no servidor front-end ou no pool de front-end. Para permitir conexões de outras implantações do XMPP, você deve configurar o XMPP no painel de controle do Lync Server. Você define as configurações na base de domínio do XMPP. Para criar uma nova associação de parceiro, faça o seguinte:

<div>

## <a name="to-create-a-new-federated-partner-or-edit-an-existing-configuration"></a>Para criar um novo parceiro federado ou editar uma configuração existente

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Federação e acesso externo**e, em seguida, clique em **parceiros federados do XMPP**.

4.  Para criar uma nova configuração, clique em **novo**

5.  Para editar uma configuração existente, selecione a configuração e clique em **Editar** .

6.  Para criar ou editar configurações para **parceiros federados do XMPP**, defina as seguintes configurações:

7.  **Domínio primário** (Obrigatório). O domínio primário é o domínio base do parceiro XMPP. Por exemplo, você digitaria **fabrikam.com** para o nome de domínio do parceiro XMPP. Esta é uma entrada obrigatória.

8.  **Descrição**. A descrição é para anotações ou outras informações de identificação para essa configuração específica. Esta entrada é opcional.

9.  **Domínios adicionais**. Domínios adicionais são domínios que fazem parte do domínio do seu parceiro XMPP que devem ser incluídos como parte da comunicação XMPP permitida. Por exemplo, se o domínio primário for **fabrikam.com**, você listará todos os outros domínios que estão sob fabrikam.com com os quais você irá se comunicar por meio de XMPP. Por exemplo, você pode inserir **Corp.fabrikam.com** e **it.fabrikam.com** para o domínio XMPP corporativo e o domínio de tecnologias de informação XMPP no domínio principal do XMPP da Fabrikam.

10. **Tipo de parceiro**. O **tipo de parceiro** é uma configuração obrigatória e oferece uma seleção de três opções em um menu suspenso. Você deve escolher uma das seguintes opções para descrever e reforçar quais contatos podem ser adicionados. Você pode selecionar:
    
      - **Federado**. Um tipo de parceiro **federado** é uma conexão confiável entre uma implantação de parceiro do Lync Server ou do Office Communications Server 2007 R2.
    
      - **Público verificado**. Um parceiro **verificado público** ocorre quando os contatos que fazem parte de uma implantação verificada pelo provedor podem ser adicionados à lista de contatos do seu usuário. Os convites podem ser enviados pelo usuário do Lync ou o usuário do Lync pode aceitar convites do contato do parceiro.
    
      - **Pública**não verificada. Uma relação não **verificada pública** implica que não há status estabelecido e verificável entre as duas implantações. Um usuário do Lync deve convidar o contato não verificado para esse contato para poder adicionar o usuário do Lync à sua lista de contatos. Por exemplo, o Google GTalk não é um serviço de XMPP verificado público como se relaciona ao Lync Server. Um usuário do GTalk não poderá adicionar o usuário do Lync como um contato, a menos que haja um convite explícito enviado pelo usuário do Lync.

11. Observações sobre negociação de fluxo e os métodos de segurança Transport Layer Security (TLS) e Authentication and Security Layer (SASL):
    
    A **base de padrões de XMPP** (xsf) e a **Internet Engineering Task Force** (IETF) definem um conjunto de regras e padrões para usar e gerenciar certificados de cliente TLS, certificados de servidor TLS e o mecanismo SASL. Usar TLS e SASL é o processo obrigatório para proteger o fluxo de XMPP. A partir do documento de padrões do XMPP **-XEP-0178**", especifica um fluxo de protocolo recomendado para usar o mecanismo externo SASL com certificados PKIX, especialmente quando um serviço XMPP indica que o TLS é obrigatório para negociar." PKIX, conforme declarado na documentação do XSF, refere-se à infraestrutura de chave pública, também conhecida como PKI.
    
    Confira o documento XSF XEP-0178 para obter mais detalhes sobre os requisitos do XMPP. Para obter detalhes, consulte "XEP-0178: práticas recomendadas para uso de SASL externo com certificados". <http://xmpp.org/extensions/xep-0178.html>
    
    Consulte o documento IETF "protocolo de mensagens extensíveis e presença (XMPP): Core", seção 5,0, negociação <http://tools.ietf.org/html/rfc6120>STARTTLS.
    
      - **Negociação de TLS**. Define as regras de negociação de TLS. Um serviço XMPP pode exigir o TLS, pode criar a TLS opcional ou você define que o TLS não é compatível. Escolher opcional deixa a necessidade de até o serviço XMPP para uma decisão obrigatória a negociação. Para ver todas as configurações e os detalhes possíveis para a negociação SASL, TLS e Dialback, incluindo configurações de erro não válidas e conhecidas-consulte [configurações de negociação para XMPP parceiros federados no Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).
        
          - <span></span>  
            **Obrigatório**. O serviço XMPP requer a negociação TLS.
        
          - <span></span>  
            **Opcional**. O serviço XMPP indica que o TLS é obrigatório para negociar.
        
          - <span></span>  
            **Sem suporte**. O serviço XMPP não dá suporte a TLS.
    
      - **Negociação SASL**. Define as regras de negociação SASL. Um serviço XMPP pode exigir SASL, pode deixar SASL opcional, ou você define que SASL não é compatível. Escolher opcional deixa o requisito para o serviço de XMPP do parceiro para uma decisão obrigatória-para-negociação.
        
        <div>
        

        > [!WARNING]  
        > SASL requer TLS. Para usar o SASL, o TLS deve ser obrigatório ou opcional. Qualquer configuração que defina SASL como obrigatório ou opcional deve ter o suporte a TLS. Ao clicar em <STRONG>confirmar</STRONG> para salvar as alterações, se você não definiu o TLS como obrigatório ou opcional, você será avisado de que a SASL deve ter suporte a TLS e suas alterações não serão salvas. Para resolver o erro, defina TLS como <STRONG>obrigatório</STRONG> ou <STRONG>opcional</STRONG>. Se o uso de SASL for opcional e o suporte de negociação TLS não for possível, você deve definir a negociação SASL para <STRONG>não compatível</STRONG>. Confirme com o serviço do XMPP qual deve ser o fluxo de negociação apropriado para TLS e SASL, ou interrupção do serviço.

        
        </div>
        
          - <span></span>  
            **Obrigatório**. O serviço XMPP requer negociação SASL.
        
          - <span></span>  
            **Opcional**. O serviço XMPP indica que a SASL é obrigatória para negociar.
        
          - <span></span>  
            **Sem suporte**. O serviço XMPP não dá suporte a SASL.
    
      - **Negociação de Dialback**. A negociação Dialback é definida pelo XSF no documento **XEP-220: Server Dialback** <http://xmpp.org/extensions/xep-0220.html>. O processo de dialback do servidor usa o sistema de nomes de domínio (DNS) e um servidor autoritativo para verificar se a solicitação veio de um parceiro XMPP válido. Para fazer isso, o servidor de origem cria uma mensagem de um tipo específico com uma chave dialback gerada e procura o servidor de recebimento no DNS. O servidor de origem envia a chave em um fluxo de XML para a pesquisa de DNS resultante, supostamente o servidor de recebimento. No recebimento da chave sobre o fluxo XML, o servidor de recebimento não responde ao servidor de origem, mas envia a chave para um servidor autoritativo conhecido. O servidor autoritativo verifica se a chave é válida ou não é válida. Se não for válido, o servidor de recebimento não responderá ao servidor de origem. Se a chave for válida, o servidor de recebimento informa ao servidor de origem que a identidade e a chave são válidas e que a conversa pode começar.
        
        Há dois Estados válidos para a **negociação do Dialback**:
        
          - <span></span>  
            **Verdadeiro**. O servidor XMPP está configurado para usar a negociação Dialback caso uma solicitação seja recebida de um servidor de origem
        
          - <span></span>  
            **Falso**. O servidor XMPP não está configurado para usar a negociação Dialback e, caso uma solicitação seja recebida de um servidor de origem, ela será ignorada

</div>

</div>

<span> </span>

</div>

</div>

</div>

