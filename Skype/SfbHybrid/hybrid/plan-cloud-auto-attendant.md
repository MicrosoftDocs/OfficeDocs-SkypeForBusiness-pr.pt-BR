---
title: Planejar um atendente automático na nuvem
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
description: Visão geral do uso de um atendente automático na nuvem com o Skype for Business Server 2019
ms.openlocfilehash: 50cd9bb8b20e44d750dab68ec6fecb30bd02e203
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918687"
---
# <a name="plan-cloud-auto-attendants"></a>Atendedores automáticos do plano da nuvem

O atendente automático usado com a Unificação de Mensagens do Exchange (Exchange Server 2013 ou Exchange Server 2016) não está mais disponível no Exchange Server 2019 ou no Exchange Online. Se sua implementação do Skype for Business Server 2019 se integrar a uma dessas versões do Exchange, você precisará usar os recursos online do Cloud Voice associados ao Sistema de Telefonia. Consulte Planejar a migração [do Skype for Business Server](plan-um-migration.md) e do Exchange Server para obter informações sobre como mover os serviços um do Exchange no Exchange Server 2013 e 2016 para a nuvem.

Isso inerentemente significa que você terá uma implementação híbrida do Skype for Business Server 2019 se quiser usar recursos de Unificação de Mensagens, como os atendentes automáticos. Confira [Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365](configure-hybrid-connectivity.md) para obter detalhes.

Um atendente automático é um serviço de nuvem que aceita chamadas de clientes e reproduz saudações, fornece opções de menu e interage com chamadores usando fala ou o teclado de discagem para rotear suas chamadas para o destino certo. Cada atendente automático recebe uma conta de recurso *(consulte* Configurar contas de [recursos)](configure-onprem-ra.md)em seu sistema do Skype for Business Server 2019 que será vinculada diretamente a um atendente automático no centro de administração do Microsoft Teams. Veja [O que são os atendentes automáticos](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) do Cloud? para obter mais detalhes sobre quais são os atendentes automáticos e quais opções e recursos existem para os atendentes automáticos.

> [!NOTE]
> Você pode atribuir vários números de serviço da Microsoft, números de Roteamento Direto ou números híbridos a um atendente automático.

Uma chamada de entrada para um atendente automático do Cloud pode tomar um dos vários caminhos, conforme mostrado aqui:

![Diagrama para os atendentes automáticos](../../SfBServer2019/media/AA-plan-concept.png)

1. Via Skype for Business Server 2019
2. Por meio [de um controlador de borda de sessão](/MicrosoftTeams/direct-routing-border-controllers.md) e [roteamento direto](/MicrosoftTeams/direct-routing-plan.md)
3. Por meio de um número online no Microsoft 365 ou no Office 365.

Confira também:

- [Configurar um atendedor automático do Cloud](/microsoftteams/create-a-phone-system-auto-attendant)
- [Responder e rotear automaticamente chamadas de entrada](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a>Requisitos

Os requisitos a seguir presumem que você já tenha implantado o Skype for Business Server 2019 em uma topologia com suporte.  Seus requisitos dependem do seu cenário:

- Se você já estiver usando a UM do Exchange online ou local e atualizar para o Skype for Business 2019, será necessário capturar a estrutura dos seus atendentes automáticos e re-crie-os na nuvem usando os atendentes automáticos na nuvem. Para obter mais informações, consulte [Movendo um atendente automático de UM do Exchange ou uma fila de chamadas para o Sistema de Telefonia.](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)

- Para uma nova configuração de atendentes automáticos na nuvem, siga as etapas descritas em [Configurar contas de recursos.](configure-onprem-ra.md)

Além dos requisitos acima, os requisitos a seguir devem ser configurados para se conectar ao serviço de atendimento automático do Microsoft Cloud:

- Conectividade híbrida. Se você já implantou o Skype for Business Server e deseja habilitar o atendente automático na nuvem para seus usuários locais, você deve garantir que tenha uma conectividade híbrida configurada entre seus ambientes locais e online. Isso algumas vezes é chamado de configuração de domínio dividido.

   Para obter mais informações, consulte Planejar a conectividade híbrida entre o Skype for Business Server e o [Microsoft 365 ou Office 365](plan-hybrid-connectivity.md) e configurar a conectividade híbrida entre o Skype for Business Server e o [Microsoft 365 ou Office 365.](configure-hybrid-connectivity.md)

- Se você estiver atribuindo um número de telefone ao seu atendente automático, precisará de uma licença do [Office 365 Enterprise E5.](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing)
- Crie uma conta [de recurso](/MicrosoftTeams/manage-resource-accounts.md) [](configure-onprem-ra.md) online ou uma conta de recurso local para cada atendente automático e atribua números de telefone e licenças. 

## <a name="migration-and-interoperability"></a>Migração e interoperabilidade

Se estiver planejando implantar o Skype for Business Server 2019 e/ou o Exchange Server 2019, planeje sua migração com cuidado para garantir o suporte contínuo para os participantes automáticos. Lembre-se do seguinte:

- O Exchange Server 2019 não oferece mais funcionalidade de UM do Exchange
- A Unificação de Mensagens do Exchange está no modo de rebaixamento
- O Skype for Business Server 2019 não se integra mais à UM do Exchange Online

Os participantes automáticos da nuvem podem ser configurados com o Skype for Business Server 2019, 2015 e 2013.

A Microsoft recomenda os seguintes caminhos de migração:

- Se você estiver atualizando para o Skype for Business Server 2019, poderá usar a UM do Exchange no Exchange Server 2013 ou 2016, mas deverá atualizar para o atendente automático na nuvem se estiver usando o Exchange Server 2019.

- Se você estiver atualizando para o Exchange Server 2019 e estiver usando versões anteriores do UM do Exchange Server para mensagens de voz do Skype for Business Server, a Microsoft recomenda atualizar para o Skype for Business Server 2019 antes da atualização da caixa de correio.  Caso contrário, os recursos de mensagens de voz serão perdidos.

Para obter mais informações sobre como planejar sua migração, consulte [Planejar a migração do Skype for Business Server e do Exchange Server.](plan-um-migration.md)

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a>Migrando um sistema de atendimento automático de UM do Exchange implementado anteriormente

Atualmente, não há suporte para migração automatizada para a nuvem de um sistema de atendimento automático de UM criado no Exchange 2013 ou 2016. Para criar um sistema de atendimento automático manualmente, você precisará:

1. Use os comandos do PowerShell de administrador do Exchange para revisar a estrutura do antigo sistema de atendimento automático, incluindo todos os atendentes automáticos aninhados e filas de chamada.  
2. Crie cópias de scripts de texto em fala ou mensagens gravadas associadas a cada nó do atendente automático da UM.
3. Crie pontos de extremidade locais para cada nó do atendente automático, incluindo a atribuição de números de telefone de teste e licenças aos objetos. Observe que agora você tem a capacidade de atribuir licenças de números de telefone locais usadas por serviços online, como o Sistema de Telefonia.
4. Implemente um novo serviço de atendimento automático na nuvem com o Microsoft Teams e o Sistema de Telefonia. Consulte [Configurar contas de recursos para](configure-onprem-ra.md) obter detalhes de implementação. Ao fazer isso, carregue os scripts de texto em fala ou as mensagens gravadas associadas a cada nó do atendente automático da UM.
5. Teste a funcionalidade do atendente automático da nuvem.
6. Reatribuir o número de telefone atribuído ao antigo atendente automático de UM do Exchange para o recém-criado principal atendente automático do Cloud.

Consulte Mover um atendente automático da UM do Exchange ou uma fila de chamadas para o Sistema de [Telefonia](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) para obter detalhes sobre essas etapas.

Quando você tiver uma estrutura sólida que atenda às suas necessidades e um script que orienta os clientes com eficiência, prossiga [para Configurar contas de recursos.](configure-onprem-ra.md)

> [!CAUTION]
> Conforme mencionado em [KB4480742,](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)não é desencorajado mover os participantes automáticos do UM do Exchange criados no Server 2015 para servidores que executam o Server 2019. Por enquanto, você teria que mantê-los em um pool do Skype for Business Server 2015 em execução no modo de coexistência.

## <a name="see-also"></a>Confira também

[Plano de migração para o Skype for Business Server e Exchange Server](plan-um-migration.md)

[Configurar contas de recurso](configure-onprem-ra.md)

[Habilitar gravação de prompt personalizado usando a interface do usuário de telefone](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Quais são os atendedores automáticos do Cloud?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Configurar um atendedor automático do Cloud](/microsoftteams/create-a-phone-system-auto-attendant)

UM do Exchange: [Atender e roteá-chamadas de entrada automaticamente](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

[Planejar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365](plan-hybrid-connectivity.md)

[Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365](configure-hybrid-connectivity.md)

[KB4480742: Chamadas para Acesso de Assinante ou atendimento automático falham com o erro "500 Server Internal" e o erro "500 Server Internal" após mover objetos de contato para o Skype for Business Server 2019](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)
