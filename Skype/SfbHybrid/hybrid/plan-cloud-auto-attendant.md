---
title: Planejar um atendedor automático na nuvem
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
description: Visão geral do uso de um atendedor automático na nuvem com o Skype for Business Server 2019
ms.openlocfilehash: d85c846a05448d8b1021bb5c1cac62c80ee1bf22
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221291"
---
# <a name="plan-cloud-auto-attendants"></a>Planejar atendedores automáticos de nuvem

O atendedor automático usado com a Unificação de mensagens do Exchange (Exchange Server 2013 ou Exchange Server 2016) não está mais disponível no Exchange Server 2019 ou no Exchange Online. Se sua implementação do Skype for Business Server 2019 se integra a qualquer uma dessas versões do Exchange, você precisará usar os recursos de voz de nuvem online associados ao sistema de telefonia. Consulte [planejar o Skype for Business Server e a migração do Exchange Server](plan-um-migration.md) para obter informações sobre como mover os serviços de um do Exchange hospedados no exchange server 2013 e 2016 para a nuvem.

Isso significa inerentemente que você terá uma implementação híbrida do Skype for Business Server 2019 se quiser usar recursos de Unificação de mensagens, como atendedores automáticos. Confira [Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365](configure-hybrid-connectivity.md) para obter detalhes.

Um atendedor automático é um serviço de nuvem que aceita chamadas de clientes e toca Saudações, fornece a eles opções de menu e interage com os chamadores usando fala ou o teclado de discagem para rotear suas chamadas para o destino correto. Cada atendedor automático é atribuído a uma *conta de recurso* (consulte [Configure Resource accounts](configure-onprem-ra.md)) no seu sistema Skype for Business Server 2019 que será vinculado diretamente a um atendedor automático no centro de administração do Microsoft Teams. Veja [o que são atendedores automáticos de nuvem?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) para obter mais detalhes sobre os atendedores automáticos e quais opções e recursos existem para atendedores automáticos.

> [!NOTE]
> Você pode atribuir vários números de serviço Microsoft, de roteamento direto ou números híbridos a um atendedor automático.

Uma chamada de entrada para um atendedor automático na nuvem pode ter um dos vários caminhos, conforme mostrado aqui:

![Diagrama de atendedores automáticos](../../SfBServer2019/media/AA-plan-concept.png)

1. Via Skype for Business Server 2019
2. Por meio de um [controlador de borda de sessão](/MicrosoftTeams/direct-routing-border-controllers.md) e [Roteamento direto](/MicrosoftTeams/direct-routing-plan.md)
3. Por meio de um número hospedado online no Microsoft 365 ou no Office 365.

Confira também:

- [Configurar um atendedor automático do Cloud](/microsoftteams/create-a-phone-system-auto-attendant)
- [Responder e rotear automaticamente chamadas de entrada](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a>Requirements

Os requisitos a seguir pressupõem que você já tenha o Skype for Business Server 2019 implantado em uma topologia com suporte.  Seus requisitos dependem do cenário:

- Se você já estiver usando UM do Exchange Online ou local e atualizar para o Skype for Business 2019, será necessário capturar a estrutura dos atendedores automáticos e recriá-los na nuvem usando atendedores automáticos da nuvem. Para obter mais informações, consulte [movendo um atendedor automático do um do Exchange ou fila de chamada para o sistema de telefonia](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system).

- Para uma nova configuração de atendedores automáticos na nuvem, siga as etapas descritas em [Configure Resource accounts](configure-onprem-ra.md).

Além dos requisitos acima, os requisitos a seguir devem ser configurados para se conectar ao serviço de atendedor automático do Microsoft Cloud:

- Conectividade híbrida. Se você já tiver o Skype for Business Server implantado e quiser habilitar o atendedor automático na nuvem para seus usuários locais, você deve garantir que a conectividade híbrida seja configurada entre seus ambientes locais e online. Isso às vezes é chamado de configuração de domínio dividido.

   Para saber mais, confira [planejar conectividade híbrida entre o Skype for Business Server e o microsoft 365 ou o office 365](plan-hybrid-connectivity.md) e [Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365](configure-hybrid-connectivity.md).

- Se você estiver atribuindo um número de telefone para o atendedor automático, precisará de uma licença [do Office 365 Enterprise E5](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing) .
- Crie uma [conta de recurso](/MicrosoftTeams/manage-resource-accounts.md) online ou conta de [recurso](configure-onprem-ra.md) local para cada atendedor automático e atribua números de telefone e licenças. 

## <a name="migration-and-interoperability"></a>Migração e interoperabilidade

Se você estiver planejando implantar o Skype for Business Server 2019 e/ou o Exchange Server 2019, deverá planejar sua migração com cuidado para garantir o suporte contínuo para atendedores automáticos. Lembre-se do seguinte:

- O Exchange Server 2019 não fornece mais funcionalidade do UM do Exchange
- A Unificação de mensagens do Exchange está no modo de aposentadoria
- O Skype for Business Server 2019 não está mais integrado ao Exchange Online UM

Os atendedores automáticos de nuvem podem ser configurados com o Skype for Business Server 2019, 2015 e 2013.

A Microsoft recomenda os seguintes caminhos de migração:

- Se você estiver atualizando para o Skype for Business Server 2019, poderá usar a UM do Exchange no Exchange Server 2013 ou 2016, mas deverá atualizar para o atendedor automático na nuvem se estiver usando o Exchange Server 2019.

- Se você estiver atualizando para o Exchange Server 2019 e estiver usando versões anteriores do Exchange Server UM para mensagens de voz do Skype for Business Server, a Microsoft recomenda que você atualize para o Skype for Business Server 2019 antes da atualização de caixa de correio.  Caso contrário, os recursos de mensagens de voz serão perdidos.

Para obter mais informações sobre como planejar sua migração, consulte [Plan for Skype for Business Server and Exchange Server Migration](plan-um-migration.md).

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a>Migrando um sistema de atendedor automático do UM do Exchange implementado anteriormente

No momento, não há suporte para migração automatizada para a nuvem de um sistema de atendedor automático da UM criado no Exchange 2013 ou 2016. Para recriar manualmente um sistema de atendedor automático, você precisará:

1. Use os comandos do PowerShell de administração do Exchange para revisar a estrutura do sistema de atendedor automático antigo, incluindo qualquer atendedor automático aninhado e filas de chamadas.  
2. Criar cópias de scripts de texto para fala ou mensagens registradas associadas a cada nó de atendedor automático da UM.
3. Criar pontos de extremidade locais para cada nó de atendedor automático, incluindo a atribuição de números de telefone de teste e licenças aos objetos. Observe que agora você tem a capacidade de atribuir licenças de números de telefone locais usadas por serviços online, como o sistema de telefonia.
4. Implementar um novo serviço de atendedor automático na nuvem com o Skype for Business Online e o sistema de telefonia. Confira [Configurar contas de recursos](configure-onprem-ra.md) para obter detalhes de implementação. Ao fazer isso, carregue os scripts de texto para fala ou as mensagens registradas associadas a cada nó de atendedor automático da UM.
5. Teste a funcionalidade do atendedor automático na nuvem.
6. Reatribua o número de telefone atribuído ao atendedor automático do UM do Exchange para o atendedor automático da nuvem principal recém-criado.

Consulte [movendo um atendedor automático do um do Exchange ou fila de chamada para o sistema de telefonia](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) para obter detalhes sobre essas etapas.

## <a name="additional-planning-resources"></a>Recursos adicionais de planejamento

O tutorial intitulado [Small Business exemplo-configurar um atendedor automático](/microsoftteams/tutorial-org-aa) passa pelo processo de reunir informações sobre as necessidades do usuário, planejar uma estrutura de atendedores automáticos e usuários (e possivelmente filas de chamadas), escrever os prompts de menu e implementar o plano no centro de administração do teams. Revise o tutorial e use os exercícios para criar seu plano.

Quando você tem uma estrutura sólida que atende às suas necessidades e um script que orienta os clientes com eficiência, prossiga para [Configurar contas de recursos](configure-onprem-ra.md).

> [!CAUTION]
> Conforme mencionado no [KB4480742](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019), a transferência de atendedores automáticos do um do Exchange criados no servidor 2015 para servidores que executam o servidor 2019 não é recomendável. Por enquanto, você teria que mantê-los em um pool 2015 do Skype for Business Server em execução no modo de coexistência.

## <a name="see-also"></a>Confira também

[Planejar a migração do Skype for Business Server e do Exchange Server](plan-um-migration.md)

[Configurar contas de recurso](configure-onprem-ra.md)

[Habilitar gravação de prompt personalizado usando a interface do usuário de telefone](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Quais são os atendedores automáticos do Cloud?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Configurar um atendedor automático do Cloud](/microsoftteams/create-a-phone-system-auto-attendant)

UM do Exchange: [atender automaticamente e rotear chamadas de entrada](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

[Planejar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365](plan-hybrid-connectivity.md)

[Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365](configure-hybrid-connectivity.md)

[KB4480742: as chamadas para acesso ao assinante ou atendedor automático falham com o Fast Busy e o erro "500 Server Internal" após mover objetos de contato para o Skype for Business Server 2019](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)
