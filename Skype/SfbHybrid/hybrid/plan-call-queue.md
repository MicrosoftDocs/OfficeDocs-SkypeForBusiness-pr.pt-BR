---
title: Planejar uma fila de chamada na nuvem
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
description: Visão geral do uso de um atendente automático na nuvem com o Skype for Business Server 2019.
ms.openlocfilehash: 629c28e752b7316a3d2e7fda0acf7f457788d6a8
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918737"
---
# <a name="plan-cloud-call-queues"></a>Planejar filas de chamadas da nuvem

A fila de chamadas na nuvem é um serviço que aceita chamadas de clientes, reproduz uma mensagem de saudação e coloca essas chamadas em uma fila de espera enquanto pesquisa uma lista pré-configurada de agentes para atender a essas chamadas. Você pode definir o conjunto de agentes em listas de distribuição habilitadas para email ou grupos de segurança. Sua organização pode ter uma ou várias filas de chamada. Filas de chamada geralmente são usadas em combinação com os atendentes automáticos.

Além disso, as filas de chamada na nuvem podem fornecer:

- Música enquanto os chamadores estão aguardando em espera
- Configurações personalizadas para o tamanho máximo da fila de chamada, tempo limite e opções de tratamento de chamada

Cada fila de chamadas recebe uma conta de recurso **(consulte** Configurar contas de [recursos)](configure-onprem-ra.md)no seu sistema do Skype for Business Server 2019 que será vinculada diretamente a uma fila de chamadas no centro de administração do Microsoft Teams. Consulte [Criar uma fila de chamada na nuvem](/MicrosoftTeams/create-a-phone-system-call-queue) para obter mais detalhes sobre o que são filas de chamada e quais opções e recursos existem para filas de chamada.

> [!NOTE]
> Você pode atribuir vários números de telefone a uma fila de chamadas, mas eles devem ser números de serviço da Microsoft, números de Roteamento Direto ou números híbridos.

## <a name="requirements"></a>Requisitos

Os requisitos a seguir presumem que você já tenha implantado o Skype for Business Server 2019 em uma topologia com suporte.  Seus requisitos dependem do seu cenário:

- Para uma nova configuração de filas de chamada na nuvem, siga as etapas descritas em [Configurar contas de recursos.](configure-onprem-ra.md) Você precisará criar contas de recursos online ou no Skype for Business Server 2019, e talvez também seja necessário associar um número de telefone à fila de chamadas.

Além dos requisitos acima, os requisitos a seguir devem ser configurados para se conectar ao serviço de fila de chamada do Microsoft Cloud:

- Conectividade híbrida. Se você já implantou o Skype for Business Server e deseja habilitar filas de chamadas na nuvem para seus usuários locais, você deve garantir que tenha uma conectividade híbrida configurada entre seus ambientes locais e online. Isso algumas vezes é chamado de configuração de domínio dividido.

   Para obter mais informações, consulte Planejar a conectividade híbrida entre o Skype for Business Server e o [Microsoft 365 ou Office 365](plan-hybrid-connectivity.md) e configurar a conectividade híbrida entre o Skype for Business Server e o [Microsoft 365 ou Office 365.](configure-hybrid-connectivity.md)

- Se você estiver atribuindo um número de telefone a uma conta de recurso, agora poderá usar a licença de Usuário Virtual do Sistema de Telefonia gratuita. Isso fornece recursos do Sistema de Telefonia para números de telefone no nível organizacional e permite que você crie recursos de atendimento automático e fila de chamadas.

- Crie uma conta de [recurso](configure-onprem-ra.md) local para cada fila de chamadas e atribua uma licença e um número de telefone, se necessário.  

Quando você tiver uma estrutura sólida que atenda às suas necessidades e um script que orienta os clientes com eficiência, prossiga [para Configurar contas de recursos.](configure-onprem-ra.md)

## <a name="see-also"></a>Confira também

[Configurar contas de recurso](configure-onprem-ra.md)

[Habilitar gravação de prompt personalizado usando a interface do usuário de telefone](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Quais são os atendedores automáticos do Cloud?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Configurar um atendedor automático do Cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[Planejar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365](plan-hybrid-connectivity.md)

[Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365](configure-hybrid-connectivity.md)

[Gerenciar contas de recursos no Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)
