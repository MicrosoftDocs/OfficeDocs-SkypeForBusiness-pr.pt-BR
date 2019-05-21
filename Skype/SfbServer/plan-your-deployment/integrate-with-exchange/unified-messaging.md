---
title: Planejar para integração de Unificação de Mensagens do Exchange no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7b22002b-7e6a-4d3f-b600-a733a7e3778a
description: 'Resumo: revise este tópico ao planejar a integração do Skype for Business Server com o Exchange 2013 ou 2016.'
ms.openlocfilehash: 3b71dd740440aeab37919bb94ef98eaeb83d4d87
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297341"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>Planejar para integração de Unificação de Mensagens do Exchange no Skype for Business

**Resumo:** Revise este tópico ao planejar a integração do Skype for Business Server com o Exchange 2013 ou 2016.

O Skype for Business Server é compatível com a integração com o Exchange Unified Messaging (UM) para combinar mensagens de voz e mensagens de email em uma única infra-estrutura de mensagens. No Exchange, o recurso de Unificação de mensagens do Exchange (UM) é uma de várias funções do Exchange Server que você pode instalar e configurar.

No Microsoft Exchange Server 2013 e no 2016, o Exchange UM é executado como um serviço em um servidor de caixa de correio do Exchange. Nas implantações de voz do Skype for Business Server Enterprise, a Unificação de mensagens combina mensagens de voz e mensagens de email em uma única loja que os usuários podem acessar a partir de um telefone (Outlook Voice Access) ou de um computador. O recurso de Unificação de mensagens e o Skype for Business Server trabalham juntos para fornecer atendimento de chamada, Outlook Voice Access e serviços de atendedor automático para usuários do Enterprise Voice.

> [!NOTE]
> O Exchange UM permanecerá disponível no Skype for Business Server 2019 quando você integrar o Skype for Business 2019 com o Exchange 2013 ou o Exchange 2016. Devido a alterações no suporte ao Exchange 2019, a integração de UM Exchange está sendo realçada em favor do recurso de correio de voz e do atendedor automático na nuvem.  Consulte [planejar o serviço de correio de voz na nuvem](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) e [planejar a migração do Skype for Business Server e do Exchange Server](../../../sfbhybrid/hybrid/plan-um-migration.md) para obter mais informações.


Para que esses recursos tenham suporte em uma implantação do Exchange UM local, você deve estar executando um dos seguintes procedimentos:

- Microsoft Exchange Server 2010 ou Service Pack mais recente (somente para o Skype for Business Server 2015)
- Microsoft Exchange Server 2013
- Microsoft Exchange Server 2016
- Microsoft Exchange Server 2019 (somente o Skype for Business Server 2019)

> [!NOTE]
> A Unificação de mensagens do Exchange como anteriormente conhecida não está mais disponível no Skype for Business Server 2019, que usa o sistema de telefonia para gravar mensagens de correio de voz e deixar a gravação em uma caixa de correio do Exchange do usuário. Para obter mais informações, consulte [planejar o serviço de correio de voz na nuvem](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) .

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a>Recursos de Unificação de mensagens integrada e Skype for Business Server

Skype for Business Server, o Enterprise Voice usa a infraestrutura de Unificação de mensagens do Exchange para fornecer atendimento de chamada, notificação de chamada, acesso de voz (incluindo caixa postal) e serviços de atendedor automático.

- **Atendimento de Chamadas** O atendimento de chamadas é o recebimento das mensagens de voz em favor dos usuários cujas ligações não são atendidas ou estão ocupados. Ele inclui uma saudação pessoal, a gravação de uma mensagem e seu envio ao Transporte de Hub do Exchange Server para ficar na fila de entrega à caixa de correio do usuário, que está armazenada no servidor de caixa de correio do Exchange.

    Se o chamador deixar uma mensagem, está é roteada até a Caixa de entrada do usuário. Se o chamador optar por não deixar uma mensagem, uma notificação de chamada perdida será armazenada na caixa de correio do usuário. Os usuários podem, então, acessar sua Caixa de entrada usando o cliente de mensagem e de colaboração do Microsoft Outlook, o Outlook Web Access, a tecnologia Exchange ActiveSync ou o Outlook Voice Access. O assunto e a prioridade das chamadas podem ser exibidos de uma maneira muito semelhante àquela do e-mail.

- **Outlook Voice Access** O Outlook Voice Access permite que um usuário do Enterprise Voice tenha acesso não apenas à caixa postal, mas também à caixa de entrada do Exchange, incluindo email, calendário e contatos de uma interface de telefonia. O número de acesso do assinante é atribuído por um administrador de UM do Exchange.

- **Atendedor automático** O atendedor automático é um recurso do Exchange UM que pode ser usado para configurar um número de telefone que os usuários externos podem discar para acessar os representantes da empresa. Especificamente, ele fornece uma série de avisos de voz que auxiliam um chamador externo a navegar por um sistema de menus. A lista de opções disponíveis é configurada no servidor do Exchange UM pelo administrador de UM do Exchange.

- **Serviços de fax** O Exchange UM inclui recursos de fax, que permitem que os usuários recebam faxes de entrada nas caixas de correio do Exchange. Para obter detalhes, consulte Unificação de [mensagens](https://go.microsoft.com/fwlink/p/?linkId=135652) na documentação do Microsoft Exchange Server.

    > [!NOTE]
    > Os serviços de fax fornecidos pelo Exchange UM servidor não estão disponíveis nas implantações do Skype for Business Server integradas ao Microsoft Exchange Server 2010, Exchange 2010 com o Service Pack mais recente, Exchange 2013 ou Exchange 2016.

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a>Componentes e topologias para mensagens unificadas local no Skype for Business Server

### <a name="exchange-server-components"></a>Componentes de Exchange Server

Para fornecer os recursos e os serviços do Exchange UM descritos em [recursos de Unificação de mensagens integrada e do Skype for Business Server](#features-of-integrated-unified-messaging-and-skype-for-business-server) para usuários do Enterprise Voice em sua organização, você deve implantar um servidor de caixa de correio do Microsoft Exchange e acesso do cliente Server, que hospeda caixas de correio de usuários e fornece um único local de armazenamento para email e caixa postal. O Exchange UM é executado como um serviço na caixa de correio do Exchange e nos servidores de acesso para cliente.

Para obter detalhes sobre os componentes de UM do Exchange no Microsoft Exchange Server 2010, consulte Implantando o [Exchange um local para fornecer o Lync Server 2013 Preview voice mail](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx) .

### <a name="supported-topologies"></a>Topologias suportadas

Você pode implantar o Skype for Business Server e o Exchange Unified Messaging (UM) na mesma floresta ou em várias florestas. Se a implantação abranger várias florestas, você deve executar as etapas de integração do Exchange para cada floresta do Exchange UM. Além disso, você deve configurar cada floresta do Microsoft Exchange para confiar na floresta do servidor do Skype for Business e na floresta do servidor do Skype for Business para confiar em cada floresta do Exchange UM. Além dessa relação de confiança de floresta, as configurações de UM do Exchange UM para todos os usuários devem ser definidas nos objetos de usuário da floresta do Skype for Business Server.

O Skype for Business Server é compatível com as seguintes topologias para a integração de UM do Exchange:

- Floresta única

- Domínio único (ou seja, uma única floresta com um único domínio). O Skype for Business Server, o Microsoft Exchange e os usuários residem no mesmo domínio.

- Vários domínios (ou seja, um domínio raiz com um ou mais domínios filhos). O Skype for Business Server e os Microsoft Exchange Servers são implantados em domínios diferentes do domínio em que você cria usuários. Os servidores Exchange UM podem ser implantados em diferentes domínios do pool do Skype for Business Server aos quais eles dão suporte.

- Várias floresta (ou seja, floresta de recursos). O Skype for Business Server é implantado em uma única floresta e os usuários são distribuídos em várias florestas. Os atributos de UM dos usuários do Exchange devem ser replicados para a floresta do Skype for Business Server.

    > [!NOTE]
    > O Exchange pode ser implantado em várias florestas. Cada organização do Exchange pode fornecer ao Exchange UM para seus usuários ou o Exchange UM pode ser implantado na mesma floresta do Skype for Business Server.

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a>Diretrizes para a integração de Unificação de mensagens local e do Skype for Business Server

As diretrizes e práticas recomendadas abaixo devem ser levadas em consideração ao implantar o Enterprise Voice:

> [!IMPORTANT]
> A Unificação de mensagens do Exchange (UM) oferece suporte ao IPv6 somente se você também estiver usando o UCMA 4.

- Implantar um servidor do Skype for Business Server Standard Edition ou um pool de front-end.

- Trabalhar com os administradores do Exchange para confirmar que tarefas cada um executará para garantir uma integração tranqüila e bem-sucedida.

- Implante as funções de servidor de caixa de correio do Exchange em cada floresta do Exchange Unified Messaging (UM) onde você deseja habilitar usuários para o Exchange UM. Para obter detalhes sobre a instalação de funções do Exchange Server, consulte a documentação do Microsoft Exchange Server 2013.

    > [!IMPORTANT]
    > Quando a UM (Exchange Unified Messaging) do Exchange está instalada, ela é configurada para usar um certificado auto-assinado. O certificado autoassinado não habilita o Skype for Business Server e o Exchange UM para confiar uns dos outros, que é por isso que é necessário solicitar um certificado separado de uma autoridade de certificação que os dois servidores confiam.

- Se o Skype for Business Server e o Exchange UM estiverem instalados em florestas diferentes, configure cada floresta do Exchange para confiar na floresta do Skype for Business Server e na floresta do servidor do Skype for Business Server para confiar em cada floresta do Exchange. Além disso, defina as configurações de UM dos usuários do Exchange UM nos objetos de usuário da floresta do Skype for Business Server, geralmente usando um script ou uma ferramenta entre florestas, como o Identity Lifecycle Manager (ILM).

- Se necessário, instale o Console de Gerenciamento do Exchange para gerenciar os servidores de Unificação de mensagens.

- Obtenha números de telefone válidos para o Outlook Voice Access e o atendedor automático.

- Se você estiver usando uma versão do Exchange UM anterior ao Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordene nomes para planos de discagem de URI de UM SIP do Exchange UM e planos de discagem de voz da empresa.

### <a name="deploying-redundant-exchange-um-servers"></a>Implantando Servidores Redundantes UM do Exchange

> [!IMPORTANT]
> Recomendamos que você implante um mínimo de dois servidores nos quais os serviços de UM do Exchange estão sendo executados para cada plano de discagem URI de UM SIP do Exchange UM que você configura para sua organização. Além de oferecer capacidade expandida, a implantação de servidores redundantes fornece alta disponibilidade. Em caso de falha do servidor, o Skype for Business Server pode ser configurado para failover para outro servidor.

As seguintes configurações de exemplo fornecem resiliência de UM do Exchange.

**Exemplo 1: Resiliência de UM do Exchange**

![Diagrama de resiliência de UM Exchange](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

No exemplo 1, os servidores UM 1 e 2 do Exchange são ativados no data center de Tukwila e os servidores UM 3 e 4 do Exchange são ativados no data center de Dublin. No caso de uma paralisação UM do Exchange em Tukwila, os registros DNS (Sistema de Nomes de Domínio) para os servidores de 1 e 2 devem ser configurados para apontar aos servidores 3 e 4, respectivamente. No caso de uma paralisação UM do Exchange em Dublin, os registros DNS para os servidores 3 e 4 devem ser configurados para apontar aos servidores 1 e 2 respectivamente.

> [!NOTE]
> Por exemplo 1, você também deve atribuir um dos seguintes certificados em cada servidor Exchange UM: Use um certificado com um curinga no nome alternativo do requerente (SAN) ou coloque o nome de domínio totalmente qualificado (FQDN) de cada um dos quatro servidores do Exchange UM na SAN.

**Exemplo 2: Resiliência de UM do Exchange**

![Diagrama de resiliência de UM Exchange](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

No exemplo 2, sob condições operacionais comuns, os servidores UM 1 e 2 do Exchange são ativados no data center de Tukwila e os servidores UM 3 e 4 do Exchange são ativados no data center de Dublin. Os quatro servidores estão incluídos no plano de discagem de URI do SIP dos usuários de Tukwila; no entanto, os servidores 3 e 4 estão desativados. No caso de uma paralisação UM Exchange em Tukwila, por exemplo, os servidores UM 1 e 2 do Exchange devem ser desativados e os servidores UM 3 e 4 do Exchange devem ser habilitados para que o tráfego UM do Exchange de Tukwila seja roteado para os servidores em Dublin.

Para obter detalhes sobre como habilitar ou desabilitar a Unificação de mensagens no Exchange 2013, consulte [integrar o exchange 2013 um com o Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=265372). As informações fornecidas aplicam-se igualmente ao Skype for Business Server.

Para obter detalhes sobre como habilitar ou desabilitar a Unificação de mensagens no Microsoft Exchange Server 2010, consulte:

- [Habilitar a Unificação de mensagens no Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204418)

- [Desabilitar a Unificação de mensagens no Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204416)

### <a name="exchange-server-2019"></a>Exchange Server 2019

A Unificação de mensagens do Exchange não está mais presente no Exchange 2019, se você tiver o Exchange 2019 e quiser a funcionalidade equivalente, será necessário usar o serviço de correio de voz da nuvem descrito no [serviço de plano de correio de voz do plano](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md).


## <a name="see-also"></a>Confira também

[Visão geral do processo de implantação para integração de Unificação de Mensagens local e Skype for Business](deployment-overview.md)
