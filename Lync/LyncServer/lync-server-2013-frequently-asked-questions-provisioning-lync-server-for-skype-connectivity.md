---
title: 'Perguntas frequentes: provisionamento do Lync Server para conectividade do Skype'
description: 'Perguntas frequentes: provisionamento do Lync Server para conectividade do Skype.'
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
ms.openlocfilehash: 1bd9e9089f4b17f8b439bf11be05bfb6ce7c6d9c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577417"
---
# <a name="frequently-asked-questions-provisioning-lync-server-2013-for-skype-connectivity"></a>Perguntas frequentes: provisionamento do Lync Server 2013 para conectividade do Skype

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2019-03-22_

A partir de abril de 2019, interromperemos a coleta e a retenção de informações de contato para clientes que foram provisionados para Federação do Skype por meio do site do pic.lync.com. Essa alteração está sendo feita para garantir que o sistema de provisionamento do pic.lync.com esteja em conformidade com as políticas de privacidade da Microsoft. 
 
Assim que essa alteração for ativa, não será mais possível fornecer atualizações de email em alterações de provisionamento pendentes. As alterações de provisionamento de PIC normalmente são concluídas em 24-48 horas após serem inseridas. Se você ainda estiver enfrentando problemas de Federação do Skype 48 horas após o envio de uma solicitação de provisionamento, envolva o suporte técnico da Microsoft para investigar ainda mais.

> [!IMPORTANT]
> Como parte dessa alteração, todas as informações de contato inseridas anteriormente serão removidas do nosso sistema até o final de abril de 2019.


**P: quais recursos são compatíveis entre o Microsoft Lync e o Skype?**

**A:** Agora, com o Skype parte da família Microsoft, novas possibilidades são abertas para estender cenários de comunicação unificada para centenas de milhões de pessoas que usam o Skype. Essa combinação permitirá que os clientes do Lync se conectem e colaborem com fornecedores, clientes e parceiros, contando com a riqueza do Lync e o alcance do Skype.

  - Mensagens instantâneas e chamadas de áudio e vídeo — chamada de áudio e vídeo federada e mensagens instantâneas entre usuários do Lync e do Skype

  - Compartilhamento de presença — informações de presença do Exchange entre contatos federados

  - Administração simples: configurações e controles para configurar comunicações federadas de acordo com as políticas e padrões da sua organização

**P: como eu me qualifique para conectar minha implantação do Lync ao Skype?**

**A:** Você estará licenciado para a conectividade do Skype se você tiver:

  - Lync Server (2010 ou 2013) mais licenças de acesso para cliente padrão do Lync Server ("CALs"; 2010 ou 2013) para os usuários e/ou dispositivos em sua organização que se conectarão ao Skype. 

  - Lync Online (como licenças autônomas ou como parte de um pacote do Office 365).No entanto, esse serviço (pic.lync.com) é apenas para o provisionamento do Lync Server e do Lync Server híbrido e de implantações do Lync Online.O provisionamento PIC do Lync Online é feito no painel de controle do Lync Online (LOCP).

**P: o que os usuários finais do Lync devem fazer para se conectar aos contatos do Skype?**

**A:** Após um domínio ser ativado e os recursos serem habilitados pelo administrador do Lync de uma organização, os usuários do Lync podem adicionar contatos do Skype às listas de contatos no cliente do Lync.

**P: o que os usuários finais do Skype devem fazer para se conectar aos contatos do Lync?**

**A:** Todos os usuários do Skype que desejam se conectar a um usuário do Lync devem ter uma conta da Microsoft associada às IDs do Skype e entrar usando a conta da Microsoft.Isso pode ser habilitado no cliente do Skype.

**P: a Federação com o Windows Live ainda está disponível?**

**A:** A partir de outubro de 2012, a Microsoft começou a ajudar os usuários do Windows Live Messenger (WLM) a mudar para o Skype, encaminhar para a desativação do WLM.O Lync continuará a dar suporte à Federação com o WLM, contanto que o WLM esteja no mercado, mas nenhuma ativação adicional do Windows Live Domain será permitida.O movimento de usuários do WLM é habilitado pelo Skype 6,0 for Mac e Windows (lançado em 25 de outubro de 2012), que permite entrar com uma conta da Microsoft (ou seja, as mesmas credenciais que o WLM). Após simplesmente entrar no Skype, o WLM Buddy lista automaticamente o preenchimento do Skype, e os usuários podem aproveitar os recursos de comunicação expandidos do Skype, como chamadas de telefones e celulares, compartilhamento de tela, chamadas de vídeo de grupo e suporte para uma ampla variedade de dispositivos.Além disso, os contatos do Lync federados dos usuários do WLM seguem a transição para o Skype com o restante de suas listas de amigos, e mensagens instantâneas entre o Skype e o Lync para esses contatos estarão disponíveis imediatamente. Os clientes do Lync não precisam fazer nada para habilitar essa continuidade de serviço.

**P: a Federação com Yahoo \! ou AOL ainda está disponível?**

**A:** Não. Federação com Yahoo\! e AOL foram contingentes com suporte do Yahoo\! e AOL.Para o Yahoo\! e AOL, o serviço terminou em 30 de junho de 2014. 

**P: posso fazer uma avaliação da conectividade do Skype antes de comprar o Lync?**

**A:** A conectividade do Skype não é oferecida com base em avaliação. No lugar de uma avaliação, os clientes do Lync com licenças qualificadas são incentivados a simplesmente se inscrever no serviço a ser testado.

**P: quais informações são necessárias para o provisionamento?**

**A:** Para enviar uma solicitação de provisionamento sob uma licença qualificada, você precisará do seguinte:

  - Número do contrato da Microsoft:
    
      - Suporte para licenciamento por volume da Microsoft: número do contrato de licença por volume da Microsoft
    
      - Rede de parceiros da Microsoft: ID de parceiro da matriz
    
      - Contrato de licenciamento do provedor de serviços: número de inscrição inicial
    
      - Serviços de alto volume: número de inscrição do produto

  - FQDNs (nomes de domínio totalmente qualificados) para o serviço de borda de acesso.
    
      - O FQDN para pelo menos um serviço de borda de acesso é necessário.
    
      - Se sua organização tiver mais de um servidor executando o serviço de borda de acesso, especifique os FQDNs de cada serviço de borda de acesso adicional. Importante: se você já especificou um FQDN para o serviço de borda de acesso e deseja alterá-lo, o provisionamento da alteração pode levar alguns dias para ser concluído e pode resultar em uma interrupção no serviço. Para evitar a interrupção do serviço, recomendamos que você mantenha o FQDN especificado anteriormente do serviço de borda de acesso.

  - Domínio (s) do protocolo de iniciação de sessão (SIP). Este é o sufixo de domínio do URI SIP que os usuários usam atualmente para mensagens instantâneas. Se sua organização tiver mais de um domínio SIP, especifique o sufixo de domínio para cada domínio usado para mensagens instantâneas. Por exemplo, para user1@contoso.com, especifique contoso.com para o domínio SIP; para o user1@example.fabrikam.com, especifique example.fabrikam.com como o domínio SIP.
    
    <div>
    

    > [!NOTE]
    > Especifique apenas o sufixo de domínio para o domínio SIP. Não especifique nenhum FQDNs, incluindo o FQDN do serviço de borda de acesso, para o domínio SIP.

    
    </div>

  - Informações de contato. Especifique um endereço de email para o administrador de cada domínio SIP especificado.

**P: como habilitar a conectividade Lync-Skype em um cenário de divisão de domínio?**

**A:** Se você tiver um cenário de divisão de domínio do Lync Online 2013 e Lync Server no local (com usuários em ambos online e no local usando o mesmo domínio SIP), habilite a conectividade Lync-Skype seguindo estas duas etapas na seguinte ordem

1.  Configure a conectividade do Lync-Skype local, conforme explicado no guia de provisionamento da PIC.

2.  Aguarde até que você veja a confirmação de que seu domínio foi provisionado pela Microsoft.

3.  Após ver a confirmação, use o centro de administração do Lync para ativar "comunicações externas". Para obter mais informações, consulte [https://office.microsoft.com/support/configure-external-communications-HA102817865.aspx?CTT=5\&origin=HA102817356](https://office.microsoft.com/support/configure-external-communications-ha102817865.aspx?ctt=5%26origin=ha102817356)

Essa ordem é importante.Você deve configurar a conectividade local antes de habilitar as comunicações no Lync Online. Se a ordem for revertida, as informações inseridas para o local no <https://pic.lync.com> não passarão. Se você já configurou o Lync Online para comunicações externas com esse domínio, desative-o, Aguarde 24 horas e comece novamente, inserindo suas informações no local <https://pic.lync.com> e, em seguida, ativando comunicações externas para o Lync Online.

**P: é possível provisionar vários FQDNs do serviço de borda de acesso para a conectividade do Skype?**

**A:** Você pode provisionar apenas um FQDN de borda de acesso para um ou mais domínios. Você pode provisionar vários FQDNs de borda de acesso, até 10 por solicitação, se eles tiverem domínios distintos.

**P: posso obter a lista de endereços de email da conta da Microsoft que você encontrou para a organização que está solicitando o provisionamento?**

**A:** Não. Esses endereços são considerados informações de identificação pessoal e não são compartilhados.

**P: Como adiciono um contato do Windows Live Messenger com uma ID que contém um domínio diferente daqueles suportados pelo Windows Live?**

**A:** Se você estiver adicionando um usuário do Windows Live Messenger com uma conta ou ID com um domínio que não seja do Windows Live, digite o endereço no seguinte formato: \<user name\> ( \<domain name\> ) @msn. com, onde \<domain name\> é o nome do domínio no endereço de email do usuário. Por exemplo, se você quisesse adicionar ted@contoso.com, usaria o seguinte formato: Ted (contoso. com) @msn. com. Para obter uma lista de domínios administrados pelo Windows Live, consulte a seção domínios com suporte em "problemas conhecidos que ocorrem com mensagens instantâneas públicas após a instalação do Live Communications Server Service Pack 1" em https://support.microsoft.com/?kbid=897567 .

**P: quanto tempo o processo de provisionamento leva?**

**A:** O provisionamento pode levar até 30 dias.

**P: como saber quando o provisionamento foi concluído?**

**A:** A Microsoft enviará uma notificação por email quando o provisionamento for concluído.

**P: como posso atualizar os detalhes de configuração ou de contato que eu envio?**

**A:** Você pode atualizar suas informações no mesmo site que usou para solicitar provisionamento, após o provisionamento ser concluído. Insira o número do contrato e clique em atualizar serviço.

</div>

<span> </span>

</div>

</div>

</div>
