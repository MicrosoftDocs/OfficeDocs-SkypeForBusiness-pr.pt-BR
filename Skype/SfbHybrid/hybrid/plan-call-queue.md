---
title: Planejar uma fila de chamadas na nuvem
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection: ''
description: Visão geral do uso de um atendedor automático de nuvem com Skype for Business Server 2019.
ms.openlocfilehash: df8013a4abc2029d585032b3d0bce810175e04f4
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615417"
---
# <a name="plan-cloud-call-queues"></a>Planejar filas de chamadas da nuvem

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

A fila de chamadas na nuvem é um serviço que aceita chamadas de clientes, reproduz uma mensagem de saudação e, em seguida, coloca essas chamadas em uma fila de espera enquanto pesquisa uma lista pré-configurada de agentes para atender a essas chamadas. Você pode definir o conjunto de agentes em listas de distribuição habilitadas para email ou grupos de segurança. Sua organização pode ter uma ou muitas filas de chamadas. Filas de chamadas geralmente são usadas em combinação com atendedores automáticos.

Além disso, as filas de chamadas na nuvem podem fornecer:

- Música enquanto os chamadores estão aguardando em espera
- Configurações personalizadas para o tamanho máximo da fila de chamadas, o tempo limite e as opções de tratamento de chamadas

Cada fila de chamadas recebe uma conta de **recurso (consulte** Configurar contas de [recursos) em](configure-onprem-ra.md) seu sistema Skype for Business Server 2019 que será vinculada diretamente a uma fila de chamadas no centro de administração do Microsoft Teams. Consulte [Criar uma fila de chamadas na nuvem](/MicrosoftTeams/create-a-phone-system-call-queue) para obter mais detalhes sobre o que são filas de chamadas e quais opções e recursos existem para filas de chamadas.

> [!NOTE]
> Você pode atribuir vários números de telefone a uma fila de chamadas, mas eles devem ser números de serviço da Microsoft, números de Roteamento Direto ou números híbridos.

## <a name="requirements"></a>Requisitos

Os requisitos a seguir pressupõem que você já tenha Skype for Business Server 2019 implantado em uma topologia com suporte.  Seus requisitos dependem do seu cenário:

- Para uma nova configuração de filas de chamadas na nuvem, siga as etapas descritas em [Configurar contas de recursos](configure-onprem-ra.md). Você precisará criar contas de recursos online ou no Skype for Business Server 2019, e talvez também seja necessário associar um número de telefone à fila de chamadas.

Além dos requisitos acima, os requisitos abaixo devem ser configurados para se conectar ao serviço de fila de chamadas do Microsoft Cloud:

- Conectividade híbrida. Se você já implantou Skype for Business Server e deseja habilitar filas de chamadas na nuvem para seus usuários locais, verifique se a conectividade híbrida está configurada entre seus ambientes locais e online. Às vezes, isso é chamado de configuração de domínio dividido.

   Para obter mais informações, consulte Planejar a conectividade híbrida entre [o Skype for Business Server e o Microsoft 365 ou Office 365](plan-hybrid-connectivity.md) e configurar a conectividade híbrida entre [o Skype for Business Server e o Microsoft 365 ou Office 365](configure-hybrid-connectivity.md).

- Se você estiver atribuindo um número de telefone a uma conta de recurso, agora poderá usar a licença gratuita Telefonia do Microsoft Teams **conta de** recurso. Isso fornece recursos do Sistema de Telefonia para números de telefone no nível organizacional e permite que você crie funcionalidades de atendedor automático e fila de chamadas.

- Crie uma conta [de recurso local](configure-onprem-ra.md) para cada fila de chamadas e atribua uma licença e um número de telefone, se necessário.  

Quando você tiver uma estrutura sólida que atenda às suas necessidades e um script que orienta os clientes com eficiência, prossiga para  [Configurar contas de recursos](configure-onprem-ra.md).

## <a name="see-also"></a>Confira também

[Configurar contas de recurso](configure-onprem-ra.md)

[Habilitar gravação de prompt personalizado usando a interface do usuário de telefone](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Quais são os atendedores automáticos do Cloud?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Configurar um atendedor automático do Cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[Planejar a conectividade híbrida entre Skype for Business Server e Microsoft 365 ou Office 365](plan-hybrid-connectivity.md)

[Configurar a conectividade híbrida entre Skype for Business Server e o Microsoft 365 ou Office 365](configure-hybrid-connectivity.md)

[Gerenciar contas de recursos no Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)