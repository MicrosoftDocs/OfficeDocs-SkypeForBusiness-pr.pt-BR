---
title: Planejar a integração de Unificação de Mensagens do Exchange no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7b22002b-7e6a-4d3f-b600-a733a7e3778a
description: 'Resumo: revise este tópico ao planejar a integração do Skype for Business Server com o Exchange 2013 ou 2016.'
ms.openlocfilehash: 95df4d0fa9d2a57385c5dd61c95bc07c07a8fa7c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096657"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>Planejar a integração de Unificação de Mensagens do Exchange no Skype for Business

**Resumo:** Revise este tópico enquanto planeja integrar o Skype for Business Server com o Exchange 2013 ou 2016.

O Skype for Business Server oferece suporte à integração com a Unificação de Mensagens (UM) do Exchange para combinar mensagens de voz e mensagens de email em uma única infraestrutura de mensagens. No Exchange, a Unificação de Mensagens do Exchange (UM) é uma das várias funções de servidor do Exchange que você pode instalar e configurar.

No Microsoft Exchange Server 2013 e 2016, a UM do Exchange é executado como um serviço em um servidor de Caixa de Correio do Exchange. Para implantações do Skype for Business Server Enterprise Voice, a Unificação de Mensagens combina mensagens de voz e mensagens de email em um único armazenamento que os usuários podem acessar de um telefone (Outlook Voice Access) ou de um computador. A Unificação de Mensagens e o Skype for Business Server trabalham juntos para fornecer serviços de atendimento de chamadas, Outlook Voice Access e atendedores automáticos aos usuários do Enterprise Voice.

> [!NOTE]
> A UM do Exchange permanece disponível no Skype for Business Server 2019 quando você integra o Skype for Business 2019 com o Exchange 2013 ou o Exchange 2016. Devido às alterações no suporte no Exchange 2019, a integração da UM do Exchange está sendo desalmada em favor dos recursos de Cloud Voicemail e Cloud Atendedor Automático.  Consulte [Plan Cloud Voicemail service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) and Plan for Skype for Business Server and Exchange Server migration [para](../../../sfbhybrid/hybrid/plan-um-migration.md) obter mais informações.


Para que esses recursos sejam suportados em uma implantação de UM do Exchange local, você deve executar um dos seguintes:

- Microsoft Exchange Server 2010 ou service pack mais recente (somente Skype for Business Server 2015)
- Microsoft Exchange Server 2013
- Microsoft Exchange Server 2016

> [!NOTE]
> A Unificação de Mensagens do Exchange, como conhecida anteriormente, não está mais disponível no Skype for Business Server 2019, que usa o Sistema de Telefonia para gravar mensagens de caixa postal e, em seguida, deixar a gravação na caixa de correio do Exchange de um usuário. Consulte [Plan Cloud Voicemail service para](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) obter mais informações.

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a>Recursos de Unificação de Mensagens integradas e Skype for Business Server

O Skype for Business Server, Enterprise Voice usa a infraestrutura da Unificação de Mensagens do Exchange (UM) para fornecer atendimento de chamadas, notificação de chamada, acesso de voz (incluindo caixa postal) e serviços de atendemento automático.

- **Atendimento de chamada** O atendimento de chamadas é o recebimento de mensagens de voz em nome de usuários cujas chamadas não são atendidas ou estão ocupadas. Ele inclui a reprodução de uma saudação pessoal, a gravação de uma mensagem e o envio da mensagem a ser en fila para entrega à caixa de correio do usuário, que é armazenada no servidor de caixa de correio do Exchange.

    Se o chamador deixar uma mensagem, está é roteada até a Caixa de entrada do usuário. Se o chamador optar por não deixar uma mensagem, uma notificação de chamada perdida será armazenada na caixa de correio do usuário. Os usuários podem, então, acessar sua Caixa de entrada usando o cliente de mensagem e de colaboração do Microsoft Outlook, o Outlook Web Access, a tecnologia Exchange ActiveSync ou o Outlook Voice Access. O assunto e a prioridade das chamadas podem ser exibidos de uma maneira muito semelhante àquela do e-mail.

- **Outlook Voice Access** Outlook Voice Access permite que um usuário Enterprise Voice acessar não apenas a caixa de correio de voz, mas também a caixa de entrada do Exchange, incluindo email, calendário e contatos de uma interface de telefonia. O número de acesso do assinante é atribuído por um administrador de UM do Exchange.

- **Atendimento automático** O atendimento automático é um recurso de UM do Exchange que pode ser usado para configurar um número de telefone que os usuários externos podem discar para alcançar representantes da empresa. Especificamente, ele fornece uma série de avisos de voz que auxiliam um chamador externo a navegar por um sistema de menus. A lista de opções disponíveis é configurada no servidor um do Exchange pelo administrador de UM do Exchange.

- **Serviços de Fax** A UM do Exchange inclui recursos de fax, que permitem que os usuários recebam faxes de entrada em suas caixas de correio do Exchange. Para obter detalhes, consulte [Unificação de Mensagens](/previous-versions/office/exchange-server-2007/bb123911(v=exchg.80)) na documentação de Microsoft Exchange Server.

    > [!NOTE]
    > Os serviços de fax fornecidos pelo servidor de UM do Exchange não estão disponíveis em implantações do Skype for Business Server integradas ao Microsoft Exchange Server 2010, Exchange 2010 com o service pack mais recente, o Exchange 2013 ou o Exchange 2016.

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a>Componentes e topologias para Unificação de Mensagens locais no Skype for Business Server

### <a name="exchange-server-components"></a>Exchange Server componentes

Para fornecer os recursos e serviços da UM do Exchange descritos em Recursos da Unificação de Mensagens integradas e do [Skype for Business Server](#features-of-integrated-unified-messaging-and-skype-for-business-server) para Enterprise Voice usuários em sua organização, você deve implantar um servidor de Caixa de Correio do Microsoft Exchange e um servidor de Acesso para Cliente, que hospeda caixas de correio de usuário e fornece um único local de armazenamento para email e caixa postal. A UM do Exchange é executado como um serviço em servidores de Caixa de Correio e Acesso para Cliente do Exchange.

Para obter detalhes sobre os componentes da UM do Exchange no Microsoft Exchange Server 2010, consulte [Deploying On-Premises Exchange UM to Provide Lync Server 2013 Preview Voice Mail](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail) .

### <a name="supported-topologies"></a>Topologias suportadas

Você pode implantar o Skype for Business Server e a Unificação de Mensagens do Exchange (UM) na mesma floresta ou em várias florestas. Se a implantação abrange várias florestas, você deve executar as etapas de integração do Exchange para cada floresta de UM do Exchange. Além disso, você deve configurar cada floresta do Microsoft Exchange para confiar na floresta do Skype for Business Server e na floresta do Skype for Business Server para confiar em cada floresta de UM do Exchange. Além dessa confiança na floresta, as configurações da UM do Exchange para todos os usuários devem ser definidas nos objetos do usuário na floresta do Skype for Business Server.

O Skype for Business Server oferece suporte às seguintes topologias para a integração da UM do Exchange:

- Floresta única

- Domínio único (ou seja, uma única floresta com um único domínio). O Skype for Business Server, o Microsoft Exchange e os usuários residem no mesmo domínio.

- Vários domínios (ou seja, um domínio raiz com um ou mais domínios filho). Os servidores do Skype for Business Server e do Microsoft Exchange são implantados em diferentes domínios do domínio em que você cria usuários. Os servidores de UM do Exchange podem ser implantados em diferentes domínios do pool do Skype for Business Server que eles suportam.

- Várias florestas (ou seja, floresta de recursos). O Skype for Business Server é implantado em uma única floresta e, em seguida, os usuários são distribuídos em várias florestas. Os atributos da UM do Exchange dos usuários devem ser replicados para a floresta do Skype for Business Server.

    > [!NOTE]
    > O Exchange pode ser implantado em várias florestas. Cada organização do Exchange pode fornecer UM do Exchange aos seus usuários, ou a UM do Exchange pode ser implantada na mesma floresta que o Skype for Business Server.

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a>Diretrizes para integrar a Unificação de Mensagens local e o Skype for Business Server

Veja a seguir diretrizes e práticas recomendadas a considerar ao implantar Enterprise Voice:

> [!IMPORTANT]
> A UM (Unificação de Mensagens) do Exchange só dá suporte a IPv6 se você também estiver usando o UCMA 4.

- Implante um servidor Standard Edition do Skype for Business Server ou um pool de Front-End.

- Trabalhar com os administradores do Exchange para confirmar que tarefas cada um executará para garantir uma integração tranqüila e bem-sucedida.

- Implante as funções de servidor de Caixa de Correio do Exchange em cada floresta de Unificação de Mensagens (UM) do Exchange onde você deseja habilitar os usuários para a UM do Exchange. Para obter detalhes sobre como instalar funções de servidor do Exchange, consulte a documentação Microsoft Exchange Server do Exchange.

    > [!IMPORTANT]
    > Quando a Unificação de Mensagens do Exchange (UM) é instalada, ela é configurada para usar um certificado auto-assinado. O certificado auto-assinado não permite que o Skype for Business Server e a UM do Exchange confiem um no outro, razão pela qual é necessário solicitar um certificado separado de uma autoridade de certificação em que ambos os servidores confiem.

- Se o Skype for Business Server e a UM do Exchange estão instalados em florestas diferentes, configure cada floresta do Exchange para confiar na floresta do Skype for Business Server e na floresta do Skype for Business Server para confiar em cada floresta do Exchange. Além disso, de definir as configurações da UM do Exchange dos usuários nos objetos do usuário na floresta do Skype for Business Server, normalmente usando um script ou uma ferramenta entre florestas, como o Gerenciador de Ciclo de Vida de Identidade (ILM).

- Se necessário, instale o Console de Gerenciamento do Exchange para gerenciar os servidores de Unificação de mensagens.

- Obtenha números de telefone válidos para o Outlook Voice Access e o atendedor automático.

- Se você estiver usando uma versão da UM do Exchange anterior ao Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordene nomes para planos de discagem SIP URI de UM do Exchange e planos de discagem Enterprise Voice de discagem.

### <a name="deploying-redundant-exchange-um-servers"></a>Implantando Servidores Redundantes UM do Exchange

> [!IMPORTANT]
> Recomendamos que você implante um mínimo de dois servidores nos quais os serviços de UM do Exchange estão sendo executados para cada plano de discagem sip de UM do Exchange que você configurar para sua organização. Além de fornecer capacidade expandida, a implantação de servidores redundantes oferece alta disponibilidade. Em caso de falha do servidor, o Skype for Business Server pode ser configurado para fail over para outro servidor.

As seguintes configurações de exemplo fornecem resiliência de UM do Exchange.

**Exemplo 1: resiliência de UM do Exchange**

![Diagrama de Resiliência de UM do Exchange](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

No exemplo 1, os servidores UM 1 e 2 do Exchange são ativados no data center de Tukwila e os servidores UM 3 e 4 do Exchange são ativados no data center de Dublin. No caso de uma paralisação da UM do Exchange em Tukwila, os registros A do Sistema de Nomes de Domínio (DNS) para os servidores 1 e 2 devem ser configurados para apontar para os servidores 3 e 4, respectivamente. No caso de uma paralisação da UM do Exchange em Dublin, os registros DNS A para os servidores 3 e 4 devem ser configurados para apontar para os servidores 1 e 2, respectivamente.

> [!NOTE]
> No Exemplo 1, você também deve atribuir um dos seguintes certificados em cada servidor de UM do Exchange: use um certificado com um curinga no Nome Alternativo do Assunto (SAN) ou coloque o FQDN (nome de domínio totalmente qualificado) de cada um dos quatro servidores de UM do Exchange na SAN.

**Exemplo 2: resiliência de UM do Exchange**

![Diagrama de Resiliência de UM do Exchange](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

No exemplo 2, sob condições operacionais comuns, os servidores UM 1 e 2 do Exchange são ativados no data center de Tukwila e os servidores UM 3 e 4 do Exchange são ativados no data center de Dublin. Os quatro servidores estão incluídos no plano de discagem de URI do SIP dos usuários de Tukwila; no entanto, os servidores 3 e 4 estão desativados. No caso de uma paralisação UM Exchange em Tukwila, por exemplo, os servidores UM 1 e 2 do Exchange devem ser desativados e os servidores UM 3 e 4 do Exchange devem ser habilitados para que o tráfego UM do Exchange de Tukwila seja roteado para os servidores em Dublin.

Para obter detalhes sobre como habilitar ou desabilitar a Unificação de Mensagens no Exchange 2013, consulte Integrar a UM do  [Exchange 2013 com o Lync Server](/exchange/checklist-integrate-exchange-2013-um-with-lync-server-exchange-2013-help). As informações fornecidas se aplica igualmente ao Skype for Business Server.

Para obter detalhes sobre como habilitar ou desabilitar a Unificação de Mensagens no Microsoft Exchange Server 2010, consulte:

- [Habilitar a Unificação de Mensagens no Exchange 2010](/previous-versions/office/exchange-server-2010/aa997908(v=exchg.141))

- [Desabilitar a Unificação de Mensagens no Exchange 2010](/previous-versions/office/exchange-server-2010/bb123529(v=exchg.141))

### <a name="exchange-server-2019"></a>Exchange Server 2019

A Unificação de Mensagens do Exchange não está mais presente no Exchange 2019, se você tiver o Exchange 2019 e quiser funcionalidade equivalente, precisará usar o serviço de Caixa Postal na Nuvem descrito em [Plan Cloud Voicemail service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md).


## <a name="see-also"></a>Confira também

[Visão geral do processo de implantação para integrar a Unificação de Mensagens local e o Skype for Business](deployment-overview.md)