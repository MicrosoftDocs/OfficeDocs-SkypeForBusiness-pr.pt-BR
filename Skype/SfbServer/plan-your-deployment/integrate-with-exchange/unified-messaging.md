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
ms.openlocfilehash: 1ae93ebeda07fccf6c9019d5bb78c63f7c722192
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810111"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>Planejar a integração de Unificação de Mensagens do Exchange no Skype for Business

**Resumo:** Revise este tópico ao planejar a integração do Skype for Business Server com o Exchange 2013 ou 2016.

O Skype for Business Server oferece suporte à integração com a Unificação de Mensagens (UM) do Exchange para combinar mensagens de voz e mensagens de email em uma única infraestrutura de mensagens. No Exchange, a Unificação de Mensagens (UM) do Exchange é uma das várias funções de servidor do Exchange que você pode instalar e configurar.

No Microsoft Exchange Server 2013 e 2016, a UM do Exchange é executado como um serviço em um servidor de Caixa de Correio do Exchange. Para implantações do Skype for Business Server Enterprise Voice, a Unificação de Mensagens combina mensagens de voz e email em um único armazenamento que os usuários podem acessar de um telefone (Outlook Voice Access) ou de um computador. A Unificação de Mensagens e o Skype for Business Server trabalham juntos para fornecer atendimento de chamadas, Outlook Voice Access e serviços de atendedores automáticos aos usuários do Enterprise Voice.

> [!NOTE]
> A UM do Exchange permanece disponível no Skype for Business Server 2019 quando você integra o Skype for Business 2019 com o Exchange 2013 ou o Exchange 2016. Devido às alterações no suporte no Exchange 2019, a integração de UM do Exchange está sendo enfatizada em favor dos recursos de Caixa Postal na Nuvem e Atendedor Automático na Nuvem.  Consulte [Planejar o serviço de Caixa Postal na](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) [Nuvem e planejar a migração do Skype for Business Server](../../../sfbhybrid/hybrid/plan-um-migration.md) e do Exchange Server para obter mais informações.


Para que esses recursos sejam suportados em uma implantação de UM do Exchange local, você deve estar executando um dos seguintes:

- Microsoft Exchange Server 2010 ou service pack mais recente (Skype for Business Server 2015 somente)
- Microsoft Exchange Server 2013
- Microsoft Exchange Server 2016

> [!NOTE]
> A Unificação de Mensagens do Exchange como anteriormente conhecida não está mais disponível no Skype for Business Server 2019, que usa o Sistema de Telefonia para gravar mensagens de caixa postal e deixar a gravação na caixa de correio do Exchange de um usuário. Consulte [Planejar o serviço de Caixa Postal na Nuvem](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) para obter mais informações.

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a>Recursos integrados da Unificação de Mensagens e do Skype for Business Server

O Skype for Business Server, Enterprise Voice, usa a infraestrutura de Unificação de Mensagens (UM) do Exchange para fornecer atendimento de chamadas, notificação de chamada, acesso de voz (incluindo caixa postal) e serviços de atendemento automático.

- **Atendimento de Chamada** O atendimento de chamadas é o recebimento de mensagens de voz em nome de usuários cujas chamadas não são atendidas ou estão ocupadas. Ele inclui a reprodução de uma saudação pessoal, a gravação de uma mensagem e o envio da mensagem a ser en fila para entrega na caixa de correio do usuário, que é armazenada no servidor de caixa de correio do Exchange.

    Se o chamador deixar uma mensagem, está é roteada até a Caixa de entrada do usuário. Se o chamador optar por não deixar uma mensagem, uma notificação de chamada perdida será armazenada na caixa de correio do usuário. Os usuários podem, então, acessar sua Caixa de entrada usando o cliente de mensagem e de colaboração do Microsoft Outlook, o Outlook Web Access, a tecnologia Exchange ActiveSync ou o Outlook Voice Access. O assunto e a prioridade das chamadas podem ser exibidos de uma maneira muito semelhante àquela do e-mail.

- **Outlook Voice Access** O Outlook Voice Access permite que um usuário do Enterprise Voice acesse não apenas a caixa postal, mas também a caixa de entrada do Exchange, incluindo email, calendário e contatos de uma interface de telefonia. O número de acesso do assinante é atribuído por um administrador de UM do Exchange.

- **Auto attendant** O atendente automático é um recurso de UM do Exchange que pode ser usado para configurar um número de telefone que usuários externos podem discar para falar com representantes da empresa. Especificamente, ele fornece uma série de avisos de voz que auxiliam um chamador externo a navegar por um sistema de menus. A lista de opções disponíveis é configurada no servidor um do Exchange pelo administrador de UM do Exchange.

- **Serviços de Fax** A UM do Exchange inclui recursos de fax, que permitem que os usuários recebam faxes recebidos em suas caixas de correio do Exchange. Para obter detalhes, [consulte Unified Messaging](https://go.microsoft.com/fwlink/p/?linkId=135652) na documentação do Microsoft Exchange Server.

    > [!NOTE]
    > Os serviços de fax fornecidos pelo servidor um do Exchange não estão disponíveis em implantações do Skype for Business Server integradas ao Microsoft Exchange Server 2010, Exchange 2010 com o service pack mais recente, Exchange 2013 ou Exchange 2016.

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a>Componentes e topologias para Unificação de Mensagens local no Skype for Business Server

### <a name="exchange-server-components"></a>Componentes do Exchange Server

Para fornecer os recursos e serviços de UM do Exchange descritos em Recursos da Unificação de Mensagens integrada e do [Skype for Business Server](#features-of-integrated-unified-messaging-and-skype-for-business-server) para usuários do Enterprise Voice em sua organização, você deve implantar um servidor de Caixa de Correio do Microsoft Exchange e um servidor de Acesso para Cliente, que hospeda caixas de correio de usuário e fornece um único local de armazenamento para email e caixa postal. A UM do Exchange é executado como um serviço em servidores de Caixa de Correio do Exchange e de Acesso para Cliente.

Para obter detalhes sobre os componentes de UM do Exchange no Microsoft Exchange Server 2010, consulte [Deploying On-Premises Exchange UM to Provide Lync Server 2013 Preview Voice Mail](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx) .

### <a name="supported-topologies"></a>Topologias suportadas

Você pode implantar o Skype for Business Server e a Unificação de Mensagens (UM) do Exchange na mesma floresta ou em várias florestas. Se a implantação abrange várias florestas, você deve executar as etapas de integração do Exchange para cada floresta um do Exchange. Além disso, você deve configurar cada floresta do Microsoft Exchange para confiar na floresta do Skype for Business Server e na floresta do Skype for Business Server para confiar em cada floresta de UM do Exchange. Além dessa confiança de floresta, as configurações de UM do Exchange para todos os usuários devem ser definidas nos objetos do usuário na floresta do Skype for Business Server.

O Skype for Business Server oferece suporte às seguintes topologias para integração de UM do Exchange:

- Floresta única

- Domínio único (ou seja, uma única floresta com um único domínio). O Skype for Business Server, o Microsoft Exchange e os usuários residem no mesmo domínio.

- Vários domínios (ou seja, um domínio raiz com um ou mais domínios filhos). O Skype for Business Server e os servidores do Microsoft Exchange são implantados em domínios diferentes do domínio onde você cria usuários. Os servidores um do Exchange podem ser implantados em domínios diferentes do pool do Skype for Business Server que eles suportam.

- Várias florestas (ou seja, floresta de recursos). O Skype for Business Server é implantado em uma única floresta e, em seguida, os usuários são distribuídos entre várias florestas. Os atributos de UM do Exchange dos usuários devem ser replicados para a floresta do Skype for Business Server.

    > [!NOTE]
    > O Exchange pode ser implantado em várias florestas. Cada organização do Exchange pode fornecer a UM do Exchange para seus usuários, ou a UM do Exchange pode ser implantada na mesma floresta que o Skype for Business Server.

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a>Diretrizes para integração de Unificação de Mensagens local e Skype for Business Server

Veja a seguir diretrizes e práticas recomendadas a considerar ao implantar o Enterprise Voice:

> [!IMPORTANT]
> A Unificação de Mensagens (UM) do Exchange só será compatível com IPv6 se você também estiver usando o UCMA 4.

- Implantar um servidor Skype for Business Server Standard Edition ou um pool de Front-End.

- Trabalhar com os administradores do Exchange para confirmar que tarefas cada um executará para garantir uma integração tranqüila e bem-sucedida.

- Implante as funções de servidor caixa de correio do Exchange em cada floresta de Unificação de Mensagens do Exchange (UM) onde você deseja habilitar os usuários para a UM do Exchange. Para obter detalhes sobre como instalar funções de servidor do Exchange, consulte a documentação do Microsoft Exchange Server.

    > [!IMPORTANT]
    > Quando a Unificação de Mensagens (UM) do Exchange é instalada, ela é configurada para usar um certificado auto-assinado. O certificado auto-assinado não permite que o Skype for Business Server e a UM do Exchange confiem um no outro, e é por isso que é necessário solicitar um certificado separado de uma autoridade de certificação em que ambos os servidores confiem.

- Se o Skype for Business Server e a UM do Exchange estão instalados em florestas diferentes, configure cada floresta do Exchange para confiar na floresta do Skype for Business Server e na floresta do Skype for Business Server para confiar em cada floresta do Exchange. Além disso, de definidas as configurações de UM do Exchange dos usuários nos objetos do usuário na floresta do Skype for Business Server, geralmente usando um script ou uma ferramenta entre florestas, como o Identity Lifecycle Manager (ILM).

- Se necessário, instale o Console de Gerenciamento do Exchange para gerenciar os servidores de Unificação de mensagens.

- Obtenha números de telefone válidos para o Outlook Voice Access e o atendedor automático.

- Se você estiver usando uma versão do UM do Exchange anterior ao Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordene nomes para planos de discagem URI SIP do Exchange e planos de discagem do Enterprise Voice.

### <a name="deploying-redundant-exchange-um-servers"></a>Implantando Servidores Redundantes UM do Exchange

> [!IMPORTANT]
> Recomendamos que você implante um mínimo de dois servidores nos quais os serviços um do Exchange estão sendo executados para cada plano de discagem URI SIP do UM do Exchange que você configurar para sua organização. Além de fornecer capacidade expandida, a implantação de servidores redundantes fornece alta disponibilidade. No caso de uma falha de servidor, o Skype for Business Server pode ser configurado para fazer fail over para outro servidor.

As seguintes configurações de exemplo fornecem resiliência de UM do Exchange.

**Exemplo 1: resiliência de UM do Exchange**

![Diagrama de resiliência de UM do Exchange](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

No exemplo 1, os servidores UM 1 e 2 do Exchange são ativados no data center de Tukwila e os servidores UM 3 e 4 do Exchange são ativados no data center de Dublin. No caso de uma paralisação UM do Exchange em Tukwila, os registros A do SISTEMA de Nomes de Domínio (DNS) para os servidores 1 e 2 devem ser configurados para apontar para os servidores 3 e 4, respectivamente. No caso de uma paralisação um exchange em Dublin, os registros DNS A para os servidores 3 e 4 devem ser configurados para apontar para os servidores 1 e 2, respectivamente.

> [!NOTE]
> For Example 1, you should also assign one of following certificates on each Exchange UM server: either use a certificate with a wildcard in the Subject Alternative Name (SAN) or Put the fully qualified domain name (FQDN) of each of the four Exchange UM servers in the SAN.

**Exemplo 2: resiliência de UM do Exchange**

![Diagrama de resiliência de UM do Exchange](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

No exemplo 2, sob condições operacionais comuns, os servidores UM 1 e 2 do Exchange são ativados no data center de Tukwila e os servidores UM 3 e 4 do Exchange são ativados no data center de Dublin. Os quatro servidores estão incluídos no plano de discagem de URI do SIP dos usuários de Tukwila; no entanto, os servidores 3 e 4 estão desativados. No caso de uma paralisação UM Exchange em Tukwila, por exemplo, os servidores UM 1 e 2 do Exchange devem ser desativados e os servidores UM 3 e 4 do Exchange devem ser habilitados para que o tráfego UM do Exchange de Tukwila seja roteado para os servidores em Dublin.

Para obter detalhes sobre como habilitar ou desabilitar a Unificação de Mensagens no Exchange 2013, consulte Integrar a UM do [Exchange 2013 com o Lync Server.](https://go.microsoft.com/fwlink/p/?LinkId=265372) As informações fornecidas se aplica igualmente ao Skype for Business Server.

Para obter detalhes sobre como habilitar ou desabilitar a Unificação de Mensagens no Microsoft Exchange Server 2010, consulte:

- [Habilitar a Unificação de Mensagens no Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204418)

- [Desabilitar a Unificação de Mensagens no Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204416)

### <a name="exchange-server-2019"></a>Exchange Server 2019

A Unificação de Mensagens do Exchange não está mais presente no Exchange 2019, se você tiver o Exchange [](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)2019 e quiser funcionalidade equivalente, será necessário usar o serviço de Caixa Postal na Nuvem descrito no serviço Plano de Caixa Postal na Nuvem.


## <a name="see-also"></a>Confira também

[Visão geral do processo de implantação para integração de Unificação de Mensagens local e Skype for Business](deployment-overview.md)
