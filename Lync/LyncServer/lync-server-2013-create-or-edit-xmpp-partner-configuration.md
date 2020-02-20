---
title: 'Lync Server 2013: criar ou editar configuração do parceiro XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit XMPP partner configuration
ms:assetid: 362dbe5e-8ee9-4aba-8c26-5907312b4a60
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552447(v=OCS.15)
ms:contentKeyID: 48679558
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 609729c65240a17b70f7ef7115bd4901f37c687a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-edit-xmpp-partner-configuration-in-lync-server-2013"></a>Criar ou editar configuração do parceiro XMPP no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-09-03_

O Microsoft Lync Server 2013 integra um proxy XMPP (Extensible Messaging and Presence Protocol) no servidor de borda e um Gateway XMPP no servidor front-end ou no pool de front-ends. Para permitir conexões de outras implantações do XMPP, você deve configurar o XMPP no painel de controle do Lync Server. Defina as configuração com base no domínio XMPP. Para criar uma nova associação de parceiro, faça o seguinte:

<div>

## <a name="to-create-a-new-federated-partner-or-edit-an-existing-configuration"></a>Para criar um novo parceiro federado ou editar uma configuração existente

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Federação e Acesso Externo** e, então, clique em**Parceiros XMPP Federados**.

4.  Para criar uma configuração, clique em **Novo**

5.  Para editar uma configuração existente, selecione-a e clique em **Editar**

6.  Para criar ou editar configurações de **Parceiros XMPP Federados**, defina as seguintes configurações:

7.  **Domínio primário** (obrigatório). O domínio primário é o domínio base do parceiro XMPP. Por exemplo, você deveria inserir **fabrikam.com** para o nome de domínio do parceiro XMPP. Esta é uma entrada necessária.

8.  **Descrição**. A descrição é para notas ou outra informação de identificação desta determinada configuração. Esta entrada é opcional.

9.  **Domínios adicionais**. Os domínios adicionais são domínios que fazem parte do seu domínio do parceiro XMPP que devem ser incluídos como parte da comunicação XMPP permitida. Por exemplo, se o domínio primário for **fabrikam.com**, será preciso listar todos os domínios que estão sob fabrikam.com e com os quais haverá comunicação por meio de XMPP. Por exemplo, é possível inserir **corp.fabrikam.com** e **it.fabrikam.com** para o domínio XMPP corporativo e para o domínio XMPP de TI sob o domínio XMPP básico fabrikam.com.

10. **Tipo de parceiro**. O **Tipo de parceiro** é uma configuração obrigatória que dá a você a seleção de três opções em um menu suspenso. Você deve escolher umas das seguintes opções para descrever e impor os contatos que podem ser adicionados. É possível selecionar entre:
    
      - **Federado**. Um tipo de parceiro **federado** é uma conexão confiável entre uma implantação de parceiro do Lync Server ou do Office Communications Server 2007 R2.
    
      - **Público verificado**. Um parceiro **Verificado publicamente** significa que há contatos que fazem parte de uma implantação, que foram verificados pelo provedor e que podem ser adicionados a sua lista de contatos de usuários. Os convites podem ser enviados do usuário do Lync ou o usuário do Lync pode aceitar convites do contato do parceiro.
    
      - **Público não verificado**. Uma relação de **Não verificado publicamente** implica na ausência de uma relação estabelecida e de status verificável entre as duas implantações. Um usuário do Lync deve convidar o contato não verificado para que o contato possa adicionar o usuário do Lync à sua lista de contatos. Por exemplo, o Google GTalk não é um serviço do XMPP verificado como se relaciona com o Lync Server. Um usuário do GTalk não será capaz de adicionar o usuário do Lync como um contato, a menos que haja um convite explícito enviado pelo usuário do Lync.

11. Observações sobre a negociação de fluxo e os métodos de segurança de TLS (protocolo TLS) e SASL (Software Authentication and Security Layer)
    
    O XSF (**XMPP Standards Foundation**) e o IETF (**Internet Engineering Task Force**) definem um conjunto de regras e padrões de uso e gerenciamento de certificados de cliente de TLS e o mecanismo SASL. O uso de TLS e SASL é o processo exigido para proteger o fluxo XMPP. Segundo o documento Padrões de XMPP **XEP-0178**, “especifica um fluxo de protocolo recomendado para uso do mecanismo EXTERNO SASL com certificados PKIX, especialmente quando um serviço XMPP indicar que o protocolo TLS é obrigatório para a negociação". PKIX, como declarado na documentação do XSF, refere-se à infraestrutura da chave pública, também conhecida como PKI.
    
    Consulte o documento do XSF XEP-0178 para obter mais detalhes sobre os requisitos de XMPP. Para obter detalhes, consulte “XEP-0178: Best Practices for Use of SASL EXTERNAL with Certificates”. <http://xmpp.org/extensions/xep-0178.html>
    
    Consulte o documento de IETF "Extensible Messaging and Presence Protocol (XMPP): Core", seção 5,0, negociação <https://tools.ietf.org/html/rfc6120>de STARTTLS.
    
      - **Negociação TLS**. Define as regras de negociação TLS. Um serviço XMPP pode exigir TLS, pode tornar o TLS opcional, ou definir que o TLS não é suportado. Escolher Opcional deixa os requisitos para o serviço XMPP para uma decisão de obrigatória para negociação. Para exibir todas as configurações e detalhes possíveis para a negociação SASL, TLS e Dialback – incluindo configurações de erro não válidas e conhecidas-consulte [configurações de negociação para parceiros federados do XMPP no Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).
        
          - <span></span>  
            **Necessário**. O serviço XMPP exige a negociação TLS.
        
          - <span></span>  
            **Opcional**. O serviço XMPP indica que o TLS é obrigatório para negociar.
        
          - <span></span>  
            **Sem suporte**. O serviço XMPP não suporta TLS.
    
      - **Negociação SASL**. Define as regras de negociação SASL. Um serviço XMPP pode exigir SASL, pode tornar SASL opcional ou definir que o SASL não é suportado. A escolha de Opcional deixa o requisito a carga do serviço XMPP parceiro para uma decisão obrigatória para negociação.
        
        <div>
        

        > [!WARNING]  
        > SASL exige o protocolo TLS. Para usar SASL, o protocolo TLS deve ser obrigatório ou opcional. Qualquer configuração que defina SASL como obrigatório ou opcional deve ter suporte ao protocolo TLS. Quando clicar em <STRONG>Confirmar</STRONG> para salvar suas alterações, se ainda não tiver definido o protocolo TLS como obrigatório ou opcional, você será avisado de que SASL deve ter suporte ao protocolo TLS e as alterações não serão salvas. Para solucionar o erro, defina o protocolo TLS como <STRONG>Obrigatório</STRONG> ou <STRONG>Opcional</STRONG>. Se o uso de SASL for opcional e o suporte à negociação do protocolo TLS não for possível, será preciso definir a negociação SASL como <STRONG>Não suportado</STRONG>. Confirme no serviço XMPP como devem ser os fluxos de negociação apropriados SASL ou do protocolo TLS ou ocorrerá uma interrupção do serviço.

        
        </div>
        
          - <span></span>  
            **Necessário**. O serviço XMPP exige negociação SASL.
        
          - <span></span>  
            **Opcional**. O serviço XMPP indica que o SASL é obrigatório para negociar.
        
          - <span></span>  
            **Sem suporte**. O serviço XMPP não suporta SASL.
    
      - **Negociação Dialback**. A negociação Dialback é definida pelo XSF no documento **XEP-220: Server Dialback** <http://xmpp.org/extensions/xep-0220.html>. O processo do servidor de rediscagem usa o DNS (Sistema de Nomes de Domínio) e um servidor autoritativo para verificar se a solicitação veio de um parceiro XMPP válido. Para isso, o servidor de origem cria uma mensagem de um tipo específico com uma chave de rediscagem gerada e pesquisa o servidor de recebimento no DNS. O servidor originador envia a chave em um fluxo XML para a pesquisa DNS resultante, provavelmente o servidor recebedor. Na receita do fluxo chave sobre XML, o servidor recebedor não responde ao servidor originador, mas envia a chave para um servidor autoritativo conhecido. O servidor autoritativo verifica se a chave é válida ou inválida. Se não for válida, o servidor recebedor não responde ao servidor originador. Se a chave é válida, o servidor recebedor informa ao servidor originador que a identidade e a chave é válida e a conversação pode começar.
        
        Existem dois estados válidos para **Negociação de discagem**:
        
          - <span></span>  
            **True**. O servidor XMPP está configurado para receber negociação de rediscagem se uma solicitação for recebida de um servidor de origem.
        
          - <span></span>  
            **False**. O servidor XMPP não está configurado para usar negociação de rediscagem se uma solicitação for recebida de um servidor de origem; a solicitação será ignorada.

</div>

</div>

<span> </span>

</div>

</div>

</div>

