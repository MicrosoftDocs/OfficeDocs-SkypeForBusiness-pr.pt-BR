---
title: Planejar o serviço de caixa postal na nuvem para usuários locais | Skype for Business Server 2019 PBX
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Este artigo descreve os benefícios, as considerações de planejamento e os requisitos para implementar o serviço de caixa postal do Microsoft Cloud. Para obter informações sobre como configurar a caixa postal em nuvem, consulte Configuring Cloud postal.
ms.openlocfilehash: 82d9473e35b5c10fd2c50b783a89df64aed62cbe
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006016"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a>Planejar o serviço de caixa postal na nuvem para usuários locais

## <a name="overview"></a>Visão Geral

Este artigo descreve os benefícios, as considerações de planejamento e os requisitos para implementar o serviço de caixa postal do Microsoft Cloud para seus usuários locais. Para obter informações sobre como configurar a caixa postal em nuvem, consulte [Configurar o serviço de caixa postal Cloud](configure-cloud-voicemail.md).

A caixa postal em nuvem substitui o local da UM (Unificação de mensagens) do Exchange em fornecer funcionalidade de mensagens de voz para usuários de voz 2019 do Skype for Business que têm caixas de correio no Exchange Server 2019 ou no Exchange Online. A caixa postal em nuvem oferece os seguintes benefícios para os usuários locais e online:

- Recursos de Teleatendimento de caixa postal e depósito com transcrição de fala avançada

- Acesso à caixa postal na caixa de correio do Exchange do usuário usando o Skype for Business online ou clientes do Outlook

- A capacidade de usar o Portal baseado na Web do Office 365 para gerenciar opções de caixa postal

- Suporte para caixas de correio do Exchange no local ou na nuvem

- Aproveitamento de Saudações do usuário existentes da Unificação de mensagens do Exchange Online

Para obter mais informações sobre a comparação de recursos, consulte [Plan for Skype for Business Server and Exchange Server Migration](plan-um-migration.md).

O Skype for Business Server 2019 continua a usar o UM do Exchange para usuários cujas caixas de correio estão em versões anteriores do Exchange Server (2013, 2016).  Compreender qual solução de caixa postal será usada com base na versão do Exchange Server e do Skype for Business Server é uma parte importante do planejamento da migração para o Skype for Business Server 2019 ou para o Exchange Server 2019. Para obter mais informações sobre migração e interoperabilidade, consulte [Plan for Skype for Business Server and Exchange Server Migration](plan-um-migration.md).

Com a caixa postal na nuvem, suas tarefas administrativas são muito simplificadas porque:

- Não é necessário configurar a função UM do Exchange.
- As tarefas de configuração para correio de voz em nuvem são mais simples.
- As atualizações da funcionalidade de caixa postal são entregues diretamente na nuvem, de forma que os usuários sempre tenham acesso aos recursos e atualizações mais recentes com menos dependência em atualizações cumulativas (CUs).
- Você tem o mesmo conjunto de controles para as caixas de correio do Exchange local e online. Para obter mais informações sobre esses controles, consulte [Configurar caixa postal do sistema de telefonia](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d?ui=en-US&rs=en-US&ad=US).

O diagrama a seguir mostra a caixa postal na nuvem em uma implantação híbrida:

![Caixa postal em nuvem do SfB](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

As chamadas não atendidas são tratadas da seguinte maneira:  

1. Para usuários hospedados no Skype for Business 2019 no local, as chamadas não atendidas são enviadas pelo Skype for Business Server local para o serviço de caixa postal em nuvem online.
2. O serviço processa a caixa postal, incluindo a transcrição.
3. O serviço então deposita a caixa postal na caixa de correio do Exchange do usuário, independentemente de a caixa de correio estar no local ou online.  
4. Os usuários podem acessar a caixa postal do Skype for Business ou do cliente Outlook.

## <a name="requirements"></a>Requirements

Os requisitos a seguir pressupõem que você já tenha o Skype for Business Server implantado em uma topologia com suporte.  Seus requisitos dependem do cenário:

- Se você já estiver usando UM do Exchange Online e atualizar para o Skype for Business 2019, será necessário modificar sua política de caixa postal hospedada e verificar se os provedores de hospedagem estão definidos corretamente. Para obter mais informações, consulte [Configurar o serviço de caixa postal na nuvem](configure-cloud-voicemail.md).

- Se você estiver usando um do Exchange no local ou se tiver uma mistura de usuários usando o UM do Exchange Online e localmente, será necessário modificar a política de caixa postal hospedada e o provedor de hospedagem.  Para obter mais informações, consulte [Configurar o serviço de caixa postal na nuvem](configure-cloud-voicemail.md).

- Para uma nova configuração de correio de voz em nuvem, siga as etapas descritas em [Configure Cloud Postal Service](configure-cloud-voicemail.md).

Além dos requisitos acima, os requisitos a seguir devem ser configurados para se conectar ao serviço de caixa postal do Microsoft Cloud:

- Conectividade híbrida. Se você já tem o Skype for Business Server implantado e deseja habilitar a caixa postal na nuvem para seus usuários locais, você deve garantir que a conectividade híbrida seja configurada entre seus ambientes locais e online. Isso às vezes é chamado de configuração de domínio dividido.

   Para saber mais, confira [planejar conectividade híbrida entre o Skype for Business Server e o office 365](plan-hybrid-connectivity.md) e [Configurar a conectividade híbrida entre o Skype for Business Server e o Office 365](configure-hybrid-connectivity.md).

- Os usuários locais devem estar habilitados para Enterprise Voice e caixa postal hospedada no Skype for Business Server.

- Uma URL do EWS (serviços Web do Exchange) externa e descoberta automática deve ser configurada ou alguns recursos de caixa postal na nuvem serão limitados.

- Se você tiver uma implantação local somente&#x2014;ou seja, somente servidores do Exchange e do Skype for Business&#x2014;mas quiser aproveitar as vantagens da caixa postal na nuvem, não será necessário ter licenças adicionais.

## <a name="migration-and-interoperability"></a>Migração e interoperabilidade

Se você estiver planejando implantar o Skype for Business Server 2019 e/ou o Exchange Server 2019, deverá planejar sua migração cuidadosamente para garantir o serviço contínuo de mensagens de voz. Lembre-se do seguinte:

- O Exchange Server 2019 não fornece mais funcionalidade do UM do Exchange
- O Skype for Business Server 2019 não está mais integrado ao Exchange Online UM

A interoperabilidade de versão e as topologias com suporte para a caixa postal em nuvem estão listadas na tabela a seguir, que compara as versões do Skype for Business Server que o usuário pode estar hospedado com a versão possível fornecendo a caixa de correio do Exchange. A caixa postal em nuvem só funciona com o Skype for Business Server e o Exchange Server 2019 ou o Exchange Online.

| | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| Skype for Business Server 2019 | UM do Exchange Server | UM do Exchange Server | Caixa postal em nuvem | Caixa postal em nuvem |
| Skype for Business Server 2015 | UM do Exchange Server | UM do Exchange Server | Caixa postal de nuvem<sup>1</sup> | Caixa postal em nuvem <br> UM do Exchange Online<sup>2</sup> |
| Lync Server 2013 <br>  | UM do Exchange Server | UM do Exchange Server | Não suportado | Caixa postal em nuvem <br> UM do Exchange Online<sup>2</sup> |

<sup>1</sup> ainda não vê essa opção? Ele está sendo implantado e talvez ainda não esteja disponível em sua organização. Confira a etapa 6, considere a possibilidade de participar, no [suporte à migração online da Unificação de mensagens do Exchange](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support
) para aceitar a conectividade planejada para a caixa postal na nuvem.

<sup>2</sup> até ser preterido. Confira [suporte à migração online da Unificação de mensagens do Exchange](../../sfbserver2019/plan/exchange-unified-messaging-online-migration-support.md) para obter mais informações. 

A Microsoft recomenda os seguintes caminhos de migração:

- Se você estiver atualizando para o Skype for Business Server 2019, poderá usar o UM do Exchange no Exchange Server 2013 ou 2016, mas deverá atualizar para a caixa postal em nuvem se estiver usando o Exchange Server 2019.
- Se você estiver atualizando para o Exchange Server 2019 e estiver usando versões anteriores do Exchange Server UM para mensagens de voz do Skype for Business Server, a Microsoft recomenda que você atualize para o Skype for Business Server 2019 antes da atualização de caixa de correio.  Caso contrário, os recursos de mensagens de voz serão perdidos.
- Se você estiver atualizando para o Skype for Business Server 2019 e tiver o Skype for Business Server 2015 configurado para caixa postal com a UM do Exchange Online, a caixa postal dos usuários migrará automaticamente da UM do Exchange Online para a caixa postal em nuvem quando sua conta for movida para Skype for Business Server 2019. 

Para obter mais informações sobre como planejar sua migração, consulte [Plan for Skype for Business Server and Exchange Server Migration](plan-um-migration.md).
