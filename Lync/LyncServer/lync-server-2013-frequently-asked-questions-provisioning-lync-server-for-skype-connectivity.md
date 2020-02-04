---
title: 'Perguntas Frequentes: Configurando Lync Server para conectividade com Skype'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Frequently Asked Questions: Provisioning Lync Server for Skype connectivity'
ms:assetid: 4d1b2bfc-780b-4b8c-afd5-11c2e59203b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440172(v=OCS.15)
ms:contentKeyID: 57793362
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7204119aca18bfeb2539b0ee5eae5bb53f38efd7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="frequently-asked-questions-provisioning-lync-server-2013-for-skype-connectivity"></a>Perguntas Frequentes: Configurando Lync Server 2013 para conectividade com Skype

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2019-03-22_

A partir de abril de 2019, interromperemos a coleta e a retenção de informações de contato para clientes provisionados para o Skype Federation pelo website da pic.lync.com. Essa alteração está sendo feita para garantir que o sistema de provisionamento do pic.lync.com respeite as políticas de privacidade da Microsoft. 
 
Depois que essa alteração ficar em tempo real, não poderemos mais fornecer atualizações de email em alterações de provisionamento pendentes. As alterações de provisionamento de PIC geralmente são concluídas dentro de 24-48 horas após serem inseridas. Se você ainda tiver problemas com a Federação do Skype 48 horas após o envio de uma solicitação de provisionamento, entre em contato com o suporte técnico da Microsoft para investigar ainda mais.

> [!IMPORTANT]
> Como parte dessa mudança, todas as informações de contato inseridas anteriormente serão removidas do nosso sistema até o final de abril de 2019.


**P: quais recursos são suportados entre o Microsoft Lync e o Skype?**

**R:** Agora que o Skype faz parte da família Microsoft, novas possibilidades abrem-se para estender cenários de comunicação unificada para centenas de milhões de pessoas que usam o Skype. Essa combinação permitirá que os clientes do Lync se conectem e colaborem com fornecedores, clientes e parceiros, contando com a riqueza do Lync e o alcance do Skype.

  - Mensagens instantâneas e chamadas de áudio e vídeo — chamadas de áudio e vídeo federadas e mensagens instantâneas entre o Lync e usuários do Skype

  - Compartilhamento de presença — troque informações de presença entre contatos federados

  - Administração simples: configurações e controles para configurar comunicações federadas de acordo com as políticas e padrões da sua organização

**P: Como faço para me qualificar para conectar a implantação do Lync ao Skype?**

**R:** Você estará licenciado para conectividade com o Skype se você tiver:

  - Lync Server (2010 ou 2013) mais licenças de acesso de cliente padrão do Lync Server ("CALs"; 2010 ou 2013) para os usuários e/ou dispositivos em sua organização que se conectarão ao Skype. 

  - Lync Online (como licenças autônomas ou como parte de um pacote do Office 365).No entanto, esse serviço (pic.lync.com) só se destina ao provisionamento do Lync Server e a implantações híbridas do Lync Server e Lync Online.O provisionamento da PIC do Lync Online é feito no painel de controle do Lync Online (LOCP).

**P: o que os usuários finais do Lync devem fazer para se conectar aos contatos do Skype?**

**R:** Depois que um domínio é ativado e os recursos são habilitados pelo administrador do Lync da organização, os usuários do Lync podem adicionar contatos do Skype às listas de contatos do cliente do Lync.

**P: o que os usuários finais da Skype devem fazer para se conectar aos contatos do Lync?**

**R:** Todos os usuários do Skype que desejam se conectar a um usuário do Lync devem ter uma conta da Microsoft associada a suas IDs Skype e entrar usando a conta da Microsoft.Isso pode ser habilitado dentro do cliente Skype.

**P: a Federação com o Windows Live ainda está disponível?**

**R:** A partir de outubro de 2012, a Microsoft começou a ajudar os usuários do Windows Live Messenger (WLM) a mudar para o Skype, encaminhar para desativá-WLM.O Lync continuará a oferecer suporte à Federação com o WLM, desde que WLM esteja no mercado, mas nenhuma ativação de domínio do Windows Live adicional será permitida.O movimento de usuários do WLM é habilitado pelo Skype 6,0 para Mac e Windows (lançado em 25 de outubro de 2012) que permite entrar com uma conta da Microsoft (por exemplo, as mesmas credenciais de WLM). Depois de conectar-se ao Skype, o WLM Buddy lista automaticamente o Skype para o Skype, e os usuários podem tirar proveito dos recursos de comunicação ampliados do Skype, como chamadas para telefones fixos e celulares, compartilhamento de tela, chamadas com vídeo em grupo e suporte para uma ampla variedade de dispositivos.Além disso, os contatos federados do Lync dos usuários do WLM seguem a transição para o Skype com o restante de suas listas de amigos, e as mensagens instantâneas entre o Skype e o Lync para estes contatos estarão disponíveis imediatamente. Os clientes do Lync não precisam fazer nada para habilitar essa continuidade de serviço.

**P: a Federação com o\! Yahoo ou AOL ainda está disponível?**

**R:** Não. Federação com o Yahoo\! e a AOL foram contingentes ao suporte do Yahoo\! e AOL.Para o Yahoo\! e AOL, o serviço foi encerrado em 30 de junho de 2014. 

**P: posso testar a conectividade do Skype antes de comprar o Lync?**

**R:** A conectividade do Skype não é oferecida com base em avaliação. No lugar de uma avaliação, os clientes do Lync com licenças qualificadas são incentivados a simplesmente se inscrever para o serviço testar.

**P: quais informações são necessárias para o provisionamento?**

**R:** Para enviar uma solicitação de provisionamento sob uma licença qualificada, você precisa do seguinte:

  - Número do contrato da Microsoft:
    
      - Suporte ao licenciamento por volume da Microsoft: número do contrato de licença por volume da Microsoft
    
      - Rede de parceiros da Microsoft: identificação de parceiro da matriz
    
      - Contrato de licenciamento do provedor de serviços: número inicial de inscrição
    
      - Serviços de alto volume: número de inscrição do produto

  - FQDNs (nomes de domínio totalmente qualificados) para o serviço de borda de acesso.
    
      - É necessário um FQDN para pelo menos um serviço de borda de acesso.
    
      - Se a sua organização tiver mais de um servidor executando o serviço de borda de acesso, especifique os FQDNs para cada serviço de borda de acesso adicional. Importante: se você especificou anteriormente um FQDN para o serviço de borda de acesso e deseja alterá-lo, o provisionamento para a alteração pode demorar vários dias para ser concluído e pode resultar em uma interrupção no serviço. Para evitar a interrupção do serviço, recomendamos que você mantenha o FQDN especificado anteriormente do serviço de borda de acesso.

  - Domínio (s) do protocolo de início de sessão (SIP). Esse é o sufixo de domínio do URI SIP que os usuários usam atualmente para mensagens instantâneas. Se a sua organização tiver mais de um domínio SIP, especifique o sufixo de domínio para cada domínio usado para mensagens instantâneas. Por exemplo, para user1@contoso.com, especifique contoso.com para o domínio SIP; para user1@example.fabrikam.com, especifique example.fabrikam.com como o domínio SIP.
    
    <div>
    

    > [!NOTE]
    > Especifique somente o sufixo do domínio para o domínio SIP. Não especifique nenhum FQDNs, incluindo o FQDN do serviço de borda de acesso, para o domínio SIP.

    
    </div>

  - Informações de contato. Especifique um endereço de email para o administrador de cada domínio SIP que você especificar.

**P: Como faço para habilitar a conectividade do Lync com o Skype em um cenário de domínio dividido?**

**R:** Se você tiver um cenário do Lync Online do Lync Online 2013 e do Lync Server local (com usuários tanto online quanto local usando o mesmo domínio SIP), habilite a conectividade do Lync-Skype fazendo essas duas etapas na seguinte ordem

1.  Configure o Lync do Lync-local conforme explicado no guia de provisionamento da PIC.

2.  Aguarde até que você veja a confirmação de que o domínio foi provisionado pela Microsoft.

3.  Depois de ver a confirmação, use o centro de administração do Lync para ativar "comunicações externas". Para obter mais informações, consulte[http://office.microsoft.com/en-us/support/configure-external-communications-HA102817865.aspx?CTT=5\&origin=HA102817356](http://office.microsoft.com/en-us/support/configure-external-communications-ha102817865.aspx?ctt=5%26origin=ha102817356)

Este pedido é importante.Você deve configurar a conectividade local antes de habilitar as comunicações no Lync Online. Se o pedido for revertido, as informações inseridas para o local no local <https://pic.lync.com> não serão passadas. Se você já configurou o Lync Online para comunicações externas com este domínio, desative-o, Aguarde 24 horas e comece novamente, inserindo suas informações no local <https://pic.lync.com> e ativando comunicações externas para o Lync Online.

**P: é possível configurar vários FQDNs do serviço de borda de acesso para conectividade do Skype?**

**R:** Você pode provisionar apenas um FQDN de borda de acesso para um ou mais domínios. Você pode provisionar vários FQDNs de borda de acesso, até 10 por solicitação, se eles tiverem domínios distintos.

**P: posso obter a lista de endereços de email da conta da Microsoft que você pode encontrar para a organização que está solicitando o provisionamento?**

**R:** Não. Esses endereços são considerados informações de identificação pessoal e não são compartilhados.

**P: Como faço para adicionar um contato do Windows Live Messenger com uma ID contendo um domínio diferente daqueles com suporte no Windows Live?**

**R:** Se você estiver adicionando um usuário do Windows Live Messenger com uma conta ou ID com um domínio que não seja do Windows Live, insira o endereço no seguinte \<formato:\>nome\<de usuário\>(nome do domínio) @msn \<. com\> , em que o nome do domínio é o nome do domínio no endereço de email do usuário. Por exemplo, se você quisesse adicionar ted@contoso.com, usaria o seguinte formato: Ted (contoso. com) @msn. com. Para obter uma lista de domínios administrados pelo Windows Live, consulte a seção domínios com suporte em "problemas conhecidos que ocorrem com o sistema de mensagens instantâneas públicas após a instalação do Live Communications http://support.microsoft.com/?kbid=897567Server Service Pack 1".

**P: quanto tempo é necessário para o processo de provisionamento?**

**R:** O provisionamento pode levar até 30 dias.

**P: como posso saber quando o provisionamento foi concluído?**

**R:** A Microsoft enviará uma notificação por email quando o provisionamento estiver concluído.

**P: Como faço para atualizar a configuração ou os detalhes do contato que eu envio?**

**R:** Você pode atualizar suas informações no mesmo site da Web que usou para solicitar provisionamento, após a conclusão do provisionamento. Digite o número do contrato e clique em atualizar serviço.

</div>

<span> </span>

</div>

</div>

</div>

