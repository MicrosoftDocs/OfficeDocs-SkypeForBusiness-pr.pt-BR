---
title: Planejar uma fila de chamada em nuvem
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Visão geral do uso de um atendedor automático na nuvem com o Skype for Business Server 2019.
ms.openlocfilehash: 2186909b3ec905d6ec6d387bcea172d8fb80287c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221301"
---
# <a name="plan-cloud-call-queues"></a>Planejar filas de chamada em nuvem

A fila de chamada em nuvem é um serviço que aceita chamadas de clientes, reproduz uma mensagem de saudação e, em seguida, coloca essas chamadas em uma fila de espera durante a pesquisa de uma lista de agentes pré-configurada para responder a essas chamadas. Você pode definir o conjunto de agentes em listas de distribuição ou grupos de segurança habilitados para email. Sua organização pode ter uma ou várias filas de chamada. As filas de chamadas normalmente são usadas em combinação com atendedores automáticos.

Além disso, as filas de chamadas em nuvem podem fornecer:

- Música enquanto os chamadores estão aguardando em espera
- Configurações personalizadas para o tamanho máximo, tempo limite e opções de tratamento de chamadas da fila de chamadas

Cada fila de chamada é atribuída a uma **conta de recurso** (consulte [Configure Resource accounts](configure-onprem-ra.md)) no seu sistema Skype for Business Server 2019 que será vinculada diretamente a uma fila de chamada no centro de administração do Microsoft Teams. Consulte [criar uma fila de chamada em nuvem](/MicrosoftTeams/create-a-phone-system-call-queue) para obter mais detalhes sobre quais filas de chamadas são e quais opções e recursos existem para filas de chamadas.

> [!NOTE]
> Você pode atribuir vários números de telefone a uma fila de chamadas, mas eles devem ser números de serviço da Microsoft, números de roteamento direto ou números híbridos.

## <a name="requirements"></a>Requirements

Os requisitos a seguir pressupõem que você já tenha o Skype for Business Server 2019 implantado em uma topologia com suporte.  Seus requisitos dependem do cenário:

- Para uma nova configuração de filas de chamada em nuvem, siga as etapas descritas em [Configure Resource accounts](configure-onprem-ra.md). Você precisará criar contas de recurso online ou no Skype for Business Server 2019, e talvez também precise associar um número de telefone à fila de chamadas.

Além dos requisitos acima, os requisitos a seguir devem ser configurados para se conectar ao serviço de fila de chamadas da nuvem da Microsoft:

- Conectividade híbrida. Se você já tiver o Skype for Business Server implantado e quiser habilitar as filas de chamadas em nuvem para seus usuários locais, você deve garantir que a conectividade híbrida seja configurada entre seus ambientes locais e online. Isso às vezes é chamado de configuração de domínio dividido.

   Para saber mais, confira [planejar conectividade híbrida entre o Skype for Business Server e o microsoft 365 ou o office 365](plan-hybrid-connectivity.md) e [Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365](configure-hybrid-connectivity.md).

- Se você estiver atribuindo um número de telefone a uma conta de recurso, agora poderá usar a licença de usuário virtual do sistema de telefonia livre de custo. Isso fornece recursos do sistema de telefonia para números de telefone no nível organizacional e permite que você crie recursos de atendedor automático e fila de chamadas.

- Crie uma [conta de recurso](configure-onprem-ra.md) local para cada fila de chamadas e atribua uma licença e um número de telefone, se necessário.  

## <a name="additional-planning-resources"></a>Recursos adicionais de planejamento

O tutorial intitulado [Small Business exemplo-configurar um atendedor automático](/microsoftteams/tutorial-org-aa) passa pelo processo de reunir informações sobre as necessidades do usuário, planejar uma estrutura de atendedores automáticos e usuários (e possivelmente filas de chamadas), escrever os prompts de menu e implementar o plano no centro de administração online. revisar o tutorial e usar os exercícios não crie seu plano.

Quando você tem uma estrutura sólida que atende às suas necessidades e um script que orienta os clientes com eficiência, prossiga para [Configurar contas de recursos](configure-onprem-ra.md).

## <a name="see-also"></a>Confira também

[Configurar contas de recurso](configure-onprem-ra.md)

[Habilitar gravação de prompt personalizado usando a interface do usuário de telefone](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Quais são os atendedores automáticos do Cloud?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Configurar um atendedor automático do Cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[Planejar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365](plan-hybrid-connectivity.md)

[Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365](configure-hybrid-connectivity.md)

[Gerenciar contas de recursos no Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)
