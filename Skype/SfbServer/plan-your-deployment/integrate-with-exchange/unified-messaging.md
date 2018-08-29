---
title: Planejar para integração de Unificação de Mensagens do Exchange no Skype for Business
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7b22002b-7e6a-4d3f-b600-a733a7e3778a
description: 'Resumo: Revise esse tópico durante o planejamento para integrar o Skype para servidor de negócios com o Exchange 2013 ou 2016.'
ms.openlocfilehash: f560df43ab6347890cc5a3b956d43ed37a55bdf3
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/29/2018
ms.locfileid: "23263897"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>Planejar para integração de Unificação de Mensagens do Exchange no Skype for Business

**Resumo:** Analise este tópico durante o planejamento para integrar o Skype para servidor de negócios com o Exchange 2013 ou 2016.

Skype para Business Server oferece suporte à integração com Exchange Unified Messaging (UM) para a combinação de mensagens de voz e mensagens de email em uma única infra-estrutura de mensagens. No Exchange, o Exchange Unified Messaging (UM) é uma das várias funções de servidor do Exchange que você pode instalar e configurar.

No Microsoft Exchange Server 2013 e 2016, UM do Exchange é executado como um serviço em um servidor de caixa de correio do Exchange. Para Skype para implantações de negócios Server Enterprise Voice, a Unificação de mensagens combina mensagens de voz e email messaging em um armazenamento que os usuários podem acessar a partir de um computador ou de um telefone (Outlook Voice Access). Unificação de mensagens e Skype para Business Server trabalham juntos para fornecer atendimento de chamadas, Outlook Voice Access e serviços de atendedor automático para usuários do Enterprise Voice.

> [!NOTE]
> UM do Exchange permanece disponível na Skype para Business Server 2019 ao integrar Skype para negócios 2019 com Exchange 2013 ou 2016 do Exchange. Devido às alterações no suporte no Exchange 2019, a integração de UM do Exchange está sendo desprovisionamento emphasised em favor de recursos de caixa postal de nuvem e atendedor automático de nuvem.  Para obter mais informações, consulte [serviço de caixa postal de nuvem planejar](../../../SfBServer2019/hybrid/plan-cloud-voicemail.md) e [Planejar Skype para Business Server e migração do Exchange Server](../../../SfBServer2019/hybrid/plan-um-migration.md) .


Para esses recursos serem suportados em uma implantação local de UM do Exchange, você deve estar executando um destes procedimentos:

- Microsoft Exchange Server 2010 ou service pack mais recente (Skype para negócios 2015 de servidor somente)
- Microsoft Exchange Server 2013
- Microsoft Exchange Server 2016
- Microsoft Exchange Server 2019 (Skype para Business Server 2019 somente)

> [!NOTE]
> Unificação de mensagens do Exchange como conhecido anteriormente não está mais disponível no Skype para Business Server 2019, que usa o sistema telefônico para registrar as mensagens de caixa postal e, em seguida, deixar a gravação na caixa de correio do Exchange do usuário. Consulte o [serviço de caixa postal de nuvem planejar](../../../SfBServer2019/hybrid/plan-cloud-voicemail.md) para obter mais informações.

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a>Recursos de Unificação de mensagens e Skype para Business Server integrado

Skype para Business Server, Enterprise Voice utiliza a infraestrutura do Exchange Unified Messaging (UM) para fornecer atendimento de chamadas, notificação de chamadas, acesso de voz (incluindo caixa postal) e serviços de atendedor automático.

- **Atendimento de Chamadas** O atendimento de chamadas é o recebimento das mensagens de voz em favor dos usuários cujas ligações não são atendidas ou estão ocupados. Ele inclui uma saudação pessoal, a gravação de uma mensagem e seu envio ao Transporte de Hub do Exchange Server para ficar na fila de entrega à caixa de correio do usuário, que está armazenada no servidor de caixa de correio do Exchange.

    Se o chamador deixar uma mensagem, está é roteada até a Caixa de entrada do usuário. Se o chamador optar por não deixar uma mensagem, uma notificação de chamada perdida será armazenada na caixa de correio do usuário. Os usuários podem, então, acessar sua Caixa de entrada usando o cliente de mensagem e de colaboração do Microsoft Outlook, o Outlook Web Access, a tecnologia Exchange ActiveSync ou o Outlook Voice Access. O assunto e a prioridade das chamadas podem ser exibidos de uma maneira muito semelhante àquela do e-mail.

- **Outlook Voice Access** Outlook Voice Access permite que um usuário do Enterprise Voice acessar não apenas de caixa postal, mas também a caixa de entrada do Exchange, incluindo email, calendário e contatos de uma interface de telefonia. O número de acesso do assinante é atribuído por um administrador de UM do Exchange.

- **Atendedor automático** Atendedor automático é um recurso de UM do Exchange que pode ser usado para configurar um número de telefone que os usuários externos pode discar para falar com representantes da empresa. Especificamente, ele fornece uma série de avisos de voz que auxiliam um chamador externo a navegar por um sistema de menus. A lista de opções disponíveis é configurada no servidor UM do Exchange pelo administrador de UM do Exchange.

- **Serviços de fax** UM do Exchange inclui recursos de fax, que permitem aos usuários receber faxes de entrada em suas caixas de correio do Exchange. Para obter detalhes, consulte [Unified Messaging](https://go.microsoft.com/fwlink/p/?linkId=135652) na documentação do Microsoft Exchange Server.

    > [!NOTE]
    > Serviços de fax fornecidos pelo servidor UM do Exchange não estão disponíveis no Skype para implantações de servidor de negócios que são integradas com o Microsoft Exchange Server 2010, Exchange 2010 com o service pack mais recente, Exchange 2013 ou 2016 do Exchange.

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a>Componentes e topologias para a Unificação de mensagens no local do Skype para Business Server

### <a name="exchange-server-components"></a>Componentes de Exchange Server

Para fornecer os recursos de UM do Exchange e os serviços descritos nos [recursos de Unificação de mensagens e Skype para Business Server integrado](#features-of-integrated-unified-messaging-and-skype-for-business-server) aos usuários do Enterprise Voice em sua organização, você deve implantar um servidor de caixa de correio do Microsoft Exchange e o acesso para cliente servidor que hospeda as caixas de correio do usuário e fornece um único local de armazenamento para email e caixa postal. UM do Exchange é executado como um serviço em servidores de acesso para cliente e caixa de correio do Exchange.

Para obter detalhes sobre os componentes UM do Exchange no Microsoft Exchange Server 2010, consulte [Implantando local UM do Exchange para fornecer do Lync Server 2013 Preview Voice Mail](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx) .

### <a name="supported-topologies"></a>Topologias suportadas

Você pode implantar Skype para Business Server e do Exchange Unified Messaging (UM) na mesma floresta ou em várias florestas. Se a implantação abranger várias florestas, você deve executar as etapas de integração do Exchange para cada floresta de UM do Exchange. Além disso, você deve configurar cada floresta do Microsoft Exchange para confiar o Skype para floresta Business Server e do Skype para floresta Business Server confiar em cada floresta de UM do Exchange. Além dessa relação de confiança de floresta, as configurações de UM do Exchange para todos os usuários devem ser definidas em objetos de usuário no Skype para floresta Business Server.

Skype para Business Server suporta as seguintes topologias para a integração de UM do Exchange:

- Floresta única

- Domínio único (ou seja, uma única floresta com um único domínio). Skype para Business Server, Microsoft Exchange e os usuários residem no mesmo domínio.

- Vários domínios (ou seja, um domínio raiz com um ou mais domínios filhos). Skype para Business Server e servidores do Microsoft Exchange são implantados em domínios diferentes do domínio onde você criar usuários. Servidores UM do Exchange podem ser implantados em domínios diferentes do Skype para pool de servidores de negócios que eles suportam.

- Várias floresta (ou seja, floresta de recursos). Skype para Business Server é implantado em uma única floresta e, em seguida, os usuários são distribuídos em várias florestas. Atributos UM do Exchange dos usuários devem ser replicados para o Skype para floresta Business Server.

    > [!NOTE]
    > O Exchange pode ser implantado em várias florestas. Cada organização do Exchange pode fornecer UM do Exchange aos seus usuários, ou UM do Exchange pode ser implantado na mesma floresta do Skype para Business Server.

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a>Políticas para integrar o local de Unificação de mensagens e Skype para Business Server

As diretrizes e práticas recomendadas abaixo devem ser levadas em consideração ao implantar o Enterprise Voice:

> [!IMPORTANT]
> Exchange Unified Messaging (UM) suporta IPv6 somente se você estiver usando UCMA 4.

- Implante um Skype para Business Server Standard Edition ou um pool de Front-End.

- Trabalhar com os administradores do Exchange para confirmar que tarefas cada um executará para garantir uma integração tranqüila e bem-sucedida.

- Implante as funções de servidor de caixa de correio do Exchange em cada floresta do Exchange Unified Messaging (UM) onde você deseja permitir que os usuários de UM do Exchange. Para obter detalhes sobre como instalar funções de servidor do Exchange, consulte a documentação do Microsoft Exchange Server 2013.

    > [!IMPORTANT]
    > Quando o Exchange Unified Messaging (UM) é instalado, ele é configurado para usar um certificado autoassinado. O certificado autoassinado não habilite Skype para Business Server e UM do Exchange confiem uns aos outros, motivo pelo qual é necessário solicitar um certificado separado de uma autoridade de certificação confiam em ambos os servidores.

- Se Skype para Business Server e UM do Exchange estiverem instalado em florestas diferentes, configure cada floresta do Exchange para confiar o Skype para floresta Business Server e do Skype para floresta Business Server confiar em cada floresta do Exchange. Além disso, defina configurações UM do Exchange dos usuários nos objetos usuário no Skype para floresta Business Server, normalmente usando um script ou uma ferramenta entre florestas, como Identity Lifecycle Manager (ILM).

- Se necessário, instale o Console de Gerenciamento do Exchange para gerenciar os servidores de Unificação de mensagens.

- Obtenha números de telefone válidos para o Outlook Voice Access e o atendedor automático.

- Se você estiver usando uma versão de UM do Exchange anteriores ao Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordene nomes para Exchange SIP URI de UM planos de discagem e planos de discagem do Enterprise Voice.

### <a name="deploying-redundant-exchange-um-servers"></a>Implantando Servidores Redundantes UM do Exchange

> [!IMPORTANT]
> Recomendamos que você implante um mínimo de dois servidores nos quais UM do Exchange services está em execução para cada plano de discagem do Exchange UM URI do SIP que podem ser definidas para sua organização. Além de oferecer capacidade expandida, a implantação de servidores redundantes fornece alta disponibilidade. No caso de uma falha do servidor, Skype para Business Server pode ser configurado para fazer failover para outro servidor.

As seguintes configurações de exemplo fornecem resiliência de UM do Exchange.

**Exemplo 1: Resiliência de UM do Exchange**

![Diagrama de resiliência de UM do Exchange](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

No exemplo 1, os servidores UM 1 e 2 do Exchange são ativados no data center de Tukwila e os servidores UM 3 e 4 do Exchange são ativados no data center de Dublin. No caso de uma paralisação UM do Exchange em Tukwila, os registros DNS (Sistema de Nomes de Domínio) para os servidores de 1 e 2 devem ser configurados para apontar aos servidores 3 e 4, respectivamente. No caso de uma paralisação UM do Exchange em Dublin, os registros DNS para os servidores 3 e 4 devem ser configurados para apontar aos servidores 1 e 2 respectivamente.

> [!NOTE]
> Por exemplo 1, você deve também atribuir um dos seguintes certificados em cada servidor UM do Exchange: use um certificado com um caractere curinga no nome de alternativo de entidade (SAN) ou colocar o nome de domínio totalmente qualificado (FQDN) de cada um os quatro servidores UM do Exchange no SAN.

**Exemplo 2: Resiliência de UM do Exchange**

![Diagrama de resiliência de UM do Exchange](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

No exemplo 2, sob condições operacionais comuns, os servidores UM 1 e 2 do Exchange são ativados no data center de Tukwila e os servidores UM 3 e 4 do Exchange são ativados no data center de Dublin. Os quatro servidores estão incluídos no plano de discagem de URI do SIP dos usuários de Tukwila; no entanto, os servidores 3 e 4 estão desativados. No caso de uma paralisação UM Exchange em Tukwila, por exemplo, os servidores UM 1 e 2 do Exchange devem ser desativados e os servidores UM 3 e 4 do Exchange devem ser habilitados para que o tráfego UM do Exchange de Tukwila seja roteado para os servidores em Dublin.

Para obter detalhes sobre como habilitar ou desabilitar o Unified Messaging no Exchange 2013, consulte [Integrate Exchange 2013 UM with Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=265372). As informações fornecidas aplicam igualmente para Skype para Business Server.

Para obter detalhes sobre como habilitar ou desabilitar o Unified Messaging no Microsoft Exchange Server 2010, consulte:

- [Habilitar a Unificação de mensagens no Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204418)

- [Desabilitar a Unificação de mensagens no Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204416)

### <a name="exchange-server-2019"></a>Exchange Server 2019

Unificação de mensagens do Exchange não estiver mais presente no Exchange 2019, se você tiver o Exchange 2019 e você deseja as funcionalidades equivalentes, que você precisará usar o serviço de correio de voz de nuvem descrito em [serviço de caixa postal planejar de nuvem](../../../SfBServer2019/hybrid/plan-cloud-voicemail.md).


## <a name="see-also"></a>Consulte também

[Visão geral do processo de implantação para integração de Unificação de Mensagens local e Skype for Business](deployment-overview.md)