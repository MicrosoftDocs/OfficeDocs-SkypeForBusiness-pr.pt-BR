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
ms.localizationpriority: medium
ms.collection: ''
description: Visão geral do uso de um atendente automático na nuvem com Skype for Business Server 2019
ms.openlocfilehash: ee79c52b8aaf4518511a51cea95b16d32008694c
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60011505"
---
# <a name="plan-cloud-auto-attendants"></a>Atendedores automáticos do plano da nuvem

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

O atendimento automático usado com Exchange Unificação de Mensagens (Exchange Server 2013 ou Exchange Server 2016) não está mais disponível no Exchange Server 2019 ou Exchange Online. Se Skype for Business Server implementação do Skype for Business Server 2019 se integra a uma dessas versões Exchange, você precisará usar os recursos online do Cloud Voice associados ao Sistema de Telefonia. Consulte [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md) for information about moving Exchange UM services homed on Exchange server 2013 and 2016 to the cloud.

Isso significa inerentemente que você terá uma implementação híbrida do Skype for Business Server 2019 se quiser usar recursos de Unificação de Mensagens, como os atendimentos automáticos. Consulte [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md) for details.

Um atendimento automático é um serviço de nuvem que aceita chamadas do cliente e reproduz saudações, fornece opções de menu e interage com chamadores usando fala ou o bloco de discagem para rotear suas chamadas para o destino certo. Cada atendente automático recebe uma conta de recurso *(consulte* [Configure resource accounts](configure-onprem-ra.md)) em seu sistema Skype for Business Server 2019 que será vinculado diretamente a um atendimento automático no centro de administração do Microsoft Teams. Consulte [Configurar um atendimento automático para](/microsoftteams/create-a-phone-system-auto-attendant) obter mais detalhes sobre quais são os atendimentos automáticos e quais opções e recursos existem para os atendimentos automáticos.

> [!NOTE]
> Você pode atribuir vários números de serviço da Microsoft, números de Roteamento Direto ou números híbridos a um atendimento automático.

Uma chamada de entrada para um atendente automático da nuvem pode tomar um dos vários caminhos, conforme mostrado aqui:

![Diagrama para os atendimentos automáticos.](../../SfBServer2019/media/AA-plan-concept.png)

1. Via Skype for Business Server 2019
2. Por meio [de um controlador de borda de sessão](/MicrosoftTeams/direct-routing-border-controllers) e [roteamento direto.](/microsoftteams/direct-routing-plan-media-bypass)
3. Por meio de um número em casa online Microsoft 365 ou Office 365.

Confira também:

- [Configurar um atendedor automático do Cloud](/microsoftteams/create-a-phone-system-auto-attendant)
- [Responder e rotear automaticamente chamadas de entrada](/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a>Requisitos

Os requisitos a seguir pressuem que você já Skype for Business Server 2019 implantado em uma topologia suportada.  Seus requisitos dependem do cenário:

- Se você já estiver usando Exchange UM online ou local e atualizar para o Skype for Business 2019, será necessário capturar a estrutura dos seus assistentes automáticos e re-criar na nuvem usando os atendimentos automáticos na nuvem. Para obter mais informações, consulte [Movendo um Exchange](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)de chamada ou fila de chamada de UM para Sistema de Telefonia .

- Para uma nova configuração de atendentes automáticos na nuvem, siga as etapas descritas em  [Configure resource accounts](configure-onprem-ra.md).

Além dos requisitos acima, os requisitos a seguir devem ser configurados para se conectar ao serviço de atendimento automático do Microsoft Cloud:

- Conectividade híbrida. Se você já tiver Skype for Business Server implantado e quiser habilitar o atendimento automático na nuvem para seus usuários locais, certifique-se de ter a conectividade híbrida configurada entre seus ambientes locais e online. Às vezes, isso é chamado de configuração de domínio dividido.

   Para obter mais informações, consulte [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and Configure hybrid [connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).

- Se você estiver atribuindo um número de telefone ao seu atendimento automático, precisará de uma licença [Office 365 Enterprise E5.](../../SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing.md)
- Crie uma conta [de recurso](/MicrosoftTeams/manage-resource-accounts) [](configure-onprem-ra.md) online ou conta de recurso local para cada atendimento automático e atribua números de telefone e licenças. 

## <a name="migration-and-interoperability"></a>Migração e interoperabilidade

Se você estiver planejando implantar o Skype for Business Server 2019 e/ou Exchange Server 2019, planeje sua migração com cuidado para garantir o suporte contínuo para os atendimentos automáticos. Lembre-se do seguinte:

- Exchange Server 2019 não fornece mais Exchange funcionalidade de UM
- Exchange A Unificação de Mensagens está no modo de aposentadoria
- Skype for Business Server 2019 não se integra mais com Exchange Online UM

Os atendentes automáticos de nuvem podem ser configurados com Skype for Business Server 2019, 2015 e 2013.

A Microsoft recomenda os seguintes caminhos de migração:

- Se você estiver atualizando para o Skype for Business Server 2019, poderá usar Exchange UM no Exchange Server 2013 ou 2016, mas deverá atualizar para o atendimento automático na nuvem se estiver usando o Exchange Server 2019.

- Se você estiver atualizando para o Exchange Server 2019 e estiver usando versões anteriores do Exchange Server UM para mensagens de voz do Skype for Business Server, a Microsoft recomenda que você atualize para o Skype for Business Server 2019 antes da atualização da caixa de correio.  Caso contrário, os recursos de mensagens de voz serão perdidos.

Para obter mais informações sobre como planejar sua migração, consulte [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a>Migrar um sistema de atendimento Exchange de UM implementado anteriormente

Atualmente, não há suporte para migração automatizada para a Nuvem de um sistema de atendimento automático de UM criado Exchange 2013 ou 2016. Para criar manualmente um sistema de atendimento automático, você precisará:

1. Use Exchange de administrador do PowerShell para revisar a estrutura do antigo sistema de atendimento automático, incluindo todos os atendimentos automáticos aninhados e filas de chamada.  
2. Crie cópias de scripts de texto para fala ou mensagens gravadas associadas a cada nó do atendimento automático da UM.
3. Crie pontos de extremidade locais para cada nó de atendimento automático, incluindo a atribuição de números de telefone de teste e licenças aos objetos. Observe que agora você tem a capacidade de atribuir licenças de números de telefone locais usados por serviços online como Sistema de Telefonia.
4. Implemente um novo serviço de atendimento automático na nuvem com Microsoft Teams e Sistema de Telefonia. Consulte [Configure resource accounts for](configure-onprem-ra.md) implementation details. Ao fazer isso, carregue os scripts de texto para fala ou as mensagens gravadas associadas a cada nó do atendimento automático da UM.
5. Teste a funcionalidade do atendimento automático na nuvem.
6. Reatribuir o número de telefone atribuído ao antigo Exchange de UM para o recém-criado atender automático da Nuvem principal.

Consulte [Mover um Exchange de chamada](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) ou um atendimento automático de UM para Sistema de Telefonia para obter detalhes sobre essas etapas.

Quando você tiver uma estrutura sólida que atenda às suas necessidades e um script que orienta os clientes com eficiência, prossiga para [Configurar contas de recursos.](configure-onprem-ra.md)

> [!CAUTION]
> Conforme mencionado no [KB4480742,](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)não é desencorajado mover Exchange os atendentes automáticos de UM criados no Server 2015 para servidores que executam o Server 2019. Por enquanto, você teria que mantê-los em um pool Skype for Business Server 2015 em execução no modo de coexistência.

## <a name="see-also"></a>Consulte Também

[Plano de migração para o Skype for Business Server e Exchange Server](plan-um-migration.md)

[Configurar contas de recurso](configure-onprem-ra.md)

[Habilitar gravação de prompt personalizado usando a interface do usuário de telefone](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Quais são os atendedores automáticos do Cloud?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Configurar um atendedor automático do Cloud](/microsoftteams/create-a-phone-system-auto-attendant)

Exchange UM: [Atende e roteia automaticamente chamadas de entrada](/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

[Planejar a conectividade híbrida entre Skype for Business Server e Microsoft 365 ou Office 365](plan-hybrid-connectivity.md)

[Configurar conectividade híbrida entre Skype for Business Server e Microsoft 365 ou Office 365](configure-hybrid-connectivity.md)

[KB4480742: as chamadas para Acesso para Assinante ou atendimento automático falham com o rápido ocupado e o erro "500 Server Internal" após mover objetos de contato para o Skype for Business Server 2019](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)
