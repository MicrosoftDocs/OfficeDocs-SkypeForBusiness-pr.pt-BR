---
title: Planejar um atendimento automático na nuvem
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
description: Visão geral do uso de um assistente automático na nuvem com o Skype for Business Server 2019
ms.openlocfilehash: b144576b3e572137a512881f4bdcd1ab0e06d0ba
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110347"
---
# <a name="plan-cloud-auto-attendants"></a>Atendedores automáticos do plano da nuvem

O atendimento automático usado com a Unificação de Mensagens do Exchange (Exchange Server 2013 ou Exchange Server 2016) não está mais disponível no Exchange Server 2019 ou no Exchange Online. Se sua implementação do Skype for Business Server 2019 se integra a qualquer uma dessas versões do Exchange, você precisará usar os recursos online do Cloud Voice associados ao Sistema de Telefonia. Consulte [Plan for Skype for Business Server and Exchange Server for information](plan-um-migration.md) about moving Exchange UM services homed on Exchange server 2013 and 2016 to the cloud.

Isso significa inerentemente que você terá uma implementação híbrida do Skype for Business Server 2019 se quiser usar recursos de Unificação de Mensagens, como os atendimentos automáticos. Confira [Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365](configure-hybrid-connectivity.md) para obter detalhes.

Um atendimento automático é um serviço de nuvem que aceita chamadas do cliente e reproduz saudações, fornece opções de menu e interage com chamadores usando fala ou o bloco de discagem para rotear suas chamadas para o destino certo. Cada atendente automático recebe uma conta de recurso *(consulte* [Configurar](configure-onprem-ra.md)contas de recursos ) em seu sistema do Skype for Business Server 2019 que será vinculado diretamente a um atendimento automático no centro de administração do Microsoft Teams. Consulte [O que são os atendimentos automáticos](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) na nuvem? para obter mais detalhes sobre quais são os atendimentos automáticos e quais opções e recursos existem para os atendimentos automáticos.

> [!NOTE]
> Você pode atribuir vários números de serviço da Microsoft, números de Roteamento Direto ou números híbridos a um atendimento automático.

Uma chamada de entrada para um atendente automático da nuvem pode tomar um dos vários caminhos, conforme mostrado aqui:

![Diagrama para os atendimentos automáticos](../../SfBServer2019/media/AA-plan-concept.png)

1. Via Skype for Business Server 2019
2. Por meio [de um controlador de borda de sessão](/MicrosoftTeams/direct-routing-border-controllers.md) e [roteamento direto](/MicrosoftTeams/direct-routing-plan.md)
3. Por meio de um número que está online no Microsoft 365 ou no Office 365.

Confira também:

- [Configurar um atendedor automático do Cloud](/microsoftteams/create-a-phone-system-auto-attendant)
- [Responder e rotear automaticamente chamadas de entrada](/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a>Requisitos

Os requisitos a seguir pressuem que você já tenha o Skype for Business Server 2019 implantado em uma topologia com suporte.  Seus requisitos dependem do cenário:

- Se você já estiver usando a UM do Exchange online ou local e atualizar para o Skype for Business 2019, será necessário capturar a estrutura dos seus assistentes automáticos e re-criar na nuvem usando os atendimentos automáticos na nuvem. Para obter mais informações, consulte [Move an Exchange UM auto attendant or call queue to Phone System](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system).

- Para uma nova configuração de atendentes automáticos na nuvem, siga as etapas descritas em  [Configure resource accounts](configure-onprem-ra.md).

Além dos requisitos acima, os requisitos a seguir devem ser configurados para se conectar ao serviço de atendimento automático do Microsoft Cloud:

- Conectividade híbrida. Se você já tiver o Skype for Business Server implantado e quiser habilitar o atendimento automático na nuvem para seus usuários locais, certifique-se de que você tem conectividade híbrida configurada entre seus ambientes locais e online. Às vezes, isso é chamado de configuração de domínio dividido.

   Para obter mais informações, consulte Plan [hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).

- Se você estiver atribuindo um número de telefone ao seu atendimento automático, precisará de uma licença do [Office 365 Enterprise E5.](../../SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing.md)
- Crie uma conta [de recurso](/MicrosoftTeams/manage-resource-accounts.md) [](configure-onprem-ra.md) online ou conta de recurso local para cada atendimento automático e atribua números de telefone e licenças. 

## <a name="migration-and-interoperability"></a>Migração e interoperabilidade

Se você estiver planejando implantar o Skype for Business Server 2019 e/ou Exchange Server 2019, planeje sua migração com cuidado para garantir o suporte contínuo para os atendimentos automáticos. Lembre-se do seguinte:

- Exchange Server 2019 não fornece mais a funcionalidade de UM do Exchange
- A Unificação de Mensagens do Exchange está no modo de aposentadoria
- O Skype for Business Server 2019 não se integra mais à UM do Exchange Online

Os atendentes automáticos de nuvem podem ser configurados com o Skype for Business Server 2019, 2015 e 2013.

A Microsoft recomenda os seguintes caminhos de migração:

- Se você estiver atualizando para o Skype for Business Server 2019, poderá usar a UM do Exchange no Exchange Server 2013 ou 2016, mas deverá atualizar para o atendimento automático na nuvem se estiver usando o Exchange Server 2019.

- Se você estiver atualizando para o Exchange Server 2019 e estiver usando versões anteriores do Exchange Server UM para mensagens de voz do Skype for Business Server, a Microsoft recomenda que você atualize para o Skype for Business Server 2019 antes da atualização da caixa de correio.  Caso contrário, os recursos de mensagens de voz serão perdidos.

Para obter mais informações sobre como planejar sua migração, consulte [Plan for Skype for Business Server e Exchange Server migration.](plan-um-migration.md)

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a>Migrando um sistema de atendimento automático de UM do Exchange implementado anteriormente

Atualmente, não há suporte para migração automatizada para a Nuvem de um sistema de atendimento automático de UM criado no Exchange 2013 ou 2016. Para criar manualmente um sistema de atendimento automático, você precisará:

1. Use os comandos do administrador do Exchange PowerShell para revisar a estrutura do antigo sistema de atendimento automático, incluindo todos os atendimentos automáticos aninhados e filas de chamada.  
2. Crie cópias de scripts de texto para fala ou mensagens gravadas associadas a cada nó do atendimento automático da UM.
3. Crie pontos de extremidade locais para cada nó de atendimento automático, incluindo a atribuição de números de telefone de teste e licenças aos objetos. Observe que agora você tem a capacidade de atribuir licenças de números de telefone locais usados por serviços online, como o Sistema de Telefonia.
4. Implemente um novo serviço de atendimento automático na nuvem com o Microsoft Teams e o Sistema de Telefonia. Consulte [Configure resource accounts for](configure-onprem-ra.md) implementation details. Ao fazer isso, carregue os scripts de texto para fala ou as mensagens gravadas associadas a cada nó do atendimento automático da UM.
5. Teste a funcionalidade do atendimento automático na nuvem.
6. Reatribua o número de telefone atribuído ao antigo atendimento automático da UM do Exchange para o recém-criado atender automático da Nuvem.

Consulte Mover um atendimento automático de UM do Exchange ou fila de chamadas para o Sistema de [Telefonia](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) para obter detalhes sobre essas etapas.

Quando você tiver uma estrutura sólida que atenda às suas necessidades e um script que orienta os clientes com eficiência, prossiga para [Configurar contas de recursos.](configure-onprem-ra.md)

> [!CAUTION]
> Conforme mencionado no [KB4480742,](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)não é desencorajado mover os atendentes automáticos da UM do Exchange criados no Server 2015 para servidores que executam o Server 2019. Por enquanto, você teria que mantê-los em um pool do Skype for Business Server 2015 em execução no modo de coexistência.

## <a name="see-also"></a>Confira também

[Plano de migração para o Skype for Business Server e Exchange Server](plan-um-migration.md)

[Configurar contas de recurso](configure-onprem-ra.md)

[Habilitar gravação de prompt personalizado usando a interface do usuário de telefone](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Quais são os atendedores automáticos do Cloud?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Configurar um atendedor automático do Cloud](/microsoftteams/create-a-phone-system-auto-attendant)

UM do Exchange: [atende automaticamente e roteia chamadas de entrada](/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

[Planejar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365](plan-hybrid-connectivity.md)

[Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365](configure-hybrid-connectivity.md)

[KB4480742: as chamadas para Acesso para Assinante ou atendimento automático falham com o rápido ocupado e o erro "500 Server Internal" após mover objetos de contato para o Skype for Business Server 2019](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)