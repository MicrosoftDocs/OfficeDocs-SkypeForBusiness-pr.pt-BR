---
title: Plano de migração para o Skype for Business Server e Exchange Server
ms.reviewer: ''
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.localizationpriority: medium
ms.prod: skype-for-business-itpro
description: Este tópico aborda o que você precisa considerar ao decidir migrar suas implantações de Skype for Business Server ou Exchange Server existentes para a versão mais recente ou para o Skype for Business Online ou Exchange Online.
ms.openlocfilehash: edc6256bc9e366b4ee75a637c41141ec3d435da2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596115"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>Plano de migração para o Skype for Business Server e Exchange Server

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Este tópico aborda o que você precisa considerar ao decidir migrar suas implantações Skype for Business Server ou Exchange Server existentes para Exchange Online. O que você pode migrar e, quando, depende muito do que você já foi definido em sua organização.

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Alterações de recursos no Exchange 2019 e Skype for Business Server 2019

Com Exchange 2019 e Skype for Business Server 2019, estamos fazendo algumas alterações nos recursos que suportamos.

### <a name="unified-messaging-support-in-exchange-2019"></a>Suporte à Unificação de Mensagens Exchange 2019

A Unificação de Mensagens (UM) foi preterida no Exchange 2019. Isso significa que Exchange 2019 não oferece mais os seguintes recursos:

- Caixa postal
- Atendedor automático

Se você implantou a função de UM no Exchange 2013 ou o serviço de UM no Exchange 2016 e deseja atualizar para o Exchange 2019, precisará migrar sua caixa postal para o serviço Caixa postal na Nuvem da Microsoft no Microsoft 365 ou Office 365. Se você deseja migrar sua caixa postal para o Caixa postal na Nuvem, confira a seção [Exchange 2013/Exchange 2016 e Skype for Business 2015 para Exchange 2019 e Skype for Business 2019 abaixo.](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019)
> [!IMPORTANT]
> Se os usuários em seus servidores Exchange 2013 ou Exchange 2016 têm caixas de correio habilitadas para UM, não os movam para o Exchange 2019 antes de atualizar seus servidores Skype for Business para o Skype for Business Server 2019 e mover os usuários para eles para evitar uma paralisação de mensagens de voz.

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Suporte ao PBX no Exchange 2019 e Skype for Business Server 2019

Caixa postal na Nuvem não fornece funcionalidade de mensagens de voz para PBXs (Private Branch Exchanges). Se você estiver usando o Exchange Server Unificação de Mensagens para PBXs e quiser atualizar para o Exchange Server 2019, precisará adotar uma das três opções listadas no blog post Nova data para a descontinuação do suporte para Controladores de Borda de Sessão no [Exchange Online Unificação](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/) de Mensagens no Blog de Equipe [do Exchange](https://blogs.technet.microsoft.com/exchange/).

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>Exchange Online Suporte à UM no Skype for Business Server 2019

Com Skype for Business Server 2019, estamos mudando de Exchange Online UM para Caixa postal na Nuvem. Quando um usuário é movido para um servidor Skype for Business 2019, ele começará automaticamente a usar Caixa postal na Nuvem quando configurado para a caixa postal hospedada. Se você estiver usando Exchange Online UM, não precisará fazer nada além de mover um usuário para o Skype for Business Server 2019 para começar a usar Caixa postal na Nuvem. No entanto, há algumas alterações na funcionalidade que você precisa estar ciente:

- A Atendedor Automático organizacional é a substituição do atendimento automático Exchange Online UM.
- As configurações de caixa postal do usuário Outlook na Web não se aplicam a Caixa postal na Nuvem.

## <a name="on-premises-um-migration-scenarios"></a>Cenários de migração de UM local

Suportamos os seguintes cenários que permitirão que você migre usuários para o Exchange 2019 e para Caixa postal na Nuvem.

- Exchange 2013/Exchange 2016 e Skype for Business Server 2015 para Exchange 2019 e Skype for Business Server 2019
- Skype for Business Server 2015 a Skype for Business Server 2019 com Exchange 2013/Exchange 2016

Os cenários a seguir exigem que não existam configurações de PBX ou SBC como parte da sua implantação atual e presumem que você tenha um UM configurado em seus servidores Exchange locais. Cada uma dessas soluções também assume que você decidiu configurar uma implantação híbrida entre seus servidores Skype for Business locais e Microsoft 365 ou Office 365. Para obter mais informações sobre Skype for Business implantações híbridas, consulte [Plan hybrid connectivity](plan-hybrid-connectivity.md).

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 e Skype for Business 2015 para Exchange 2019 e Skype for Business 2019

Nesse cenário, você deseja migrar seus servidores Exchange 2013, Exchange 2016 e Skype for Business 2015 para o Exchange 2019 e Skype for Business 2019.

Conforme mencionado anteriormente neste tópico, Exchange 2019 não inclui mais o serviço de UM. Isso significa que, para todas as caixas de correio que você deseja mover para o Exchange 2019, você precisa usar o Caixa postal na Nuvem para substituir a funcionalidade fornecida pelo serviço de UM. Quando você configura o Skype for Business Server 2019 e uma implantação híbrida entre ele e Microsoft 365 ou Office 365, o Caixa postal na Nuvem substitui esses serviços de caixa postal Exchange um.

A ordem na qual você move os usuários para o Exchange 2019 e Skype for Business Server 2019 é fundamental para garantir que a funcionalidade de caixa postal permaneça disponível para todos os usuários. Onde a caixa postal é processada também é determinada por onde Exchange e Skype for Business caixas de correio e usuários estão localizados. Confira a tabela a seguir para ver quais combinações de Exchange e Skype for Business Server são suportadas e onde a caixa postal é processada.

| Caixa de correio localizada em:            | Usuário localizado no Skype for Business Server 2015 | Usuário localizado no Skype for Business Server 2019  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | UM do Exchange                             | UM do Exchange                              |
| Exchange 2019                  | Sem suporte                           | Caixa Postal na Nuvem                          |

Antes de iniciar a migração para Skype for Business Server 2019 e Exchange 2019, lembre-se do seguinte:

- A caixa postal na nuvem não dá suporte a organizações Atendedor Automático ga. Se você quiser que as caixas de correio movidas para o Caixa postal na Nuvem continuem disponíveis por meio do atendimento automático, você precisará manter pelo menos um servidor Exchange 2013 ou Exchange 2016 executando a função ou serviço de UM disponível.
- Você precisa configurar pelo menos um servidor Skype for Business 2019 e mover usuários para esse servidor antes de mover suas caixas de correio para Exchange 2019.  Se não fizer isso, essas caixas de correio não poderão receber mensagens de caixa postal.
- As chamadas enviadas para a caixa postal serão transferidas para Caixa postal na Nuvem onde serão gravadas. Depois que a chamada terminar, a mensagem de caixa postal será enviada para a caixa de correio do destinatário no servidor local Exchange 2019. Você precisa levar esse tráfego de voz em consideração ao determinar se sua conectividade com a Internet é suficiente para dar suporte a Caixa postal na Nuvem.

Aqui estão as etapas de alto nível para concluir essa migração.

1. Instale e configure Skype for Business Server 2019 em um novo servidor.
2. Atualize sua configuração de implantação híbrida para incluir o novo Skype for Business 2019.
3. Instale e configure Exchange Server 2019 em um novo servidor.
4. Mova os usuários do servidor Skype for Business 2015 para o servidor Skype for Business 2019.
5. De definir a política de caixa postal hospedada para cada usuário movido para Skype for Business Server 2019 para usar Caixa postal na Nuvem.
6. Mover caixas de correio do servidor Exchange 2013 ou Exchange 2016 para seu servidor Exchange 2019.
7. Desative seus servidores Skype for Business 2015 depois que o último usuário tiver sido movido para fora deles.
8. Desative o Exchange 2013 ou Exchange 2016 após a última caixa de correio ter sido movida para fora deles.

    > [!IMPORTANT]
    > Se você depender de um atendente automático, mantenha pelo menos um Exchange 2013 ou Exchange 2016 em execução e disponível.

### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>Skype for Business Server 2015 a Skype for Business Server 2019 com Exchange 2013/Exchange 2016

Nesse cenário, você deseja migrar seu servidor Skype for Business 2015 existente para o Skype for Business Server 2019, mas permanecer no Exchange 2013 ou Exchange 2016.

Quando o Skype for Business Server 2015 e o Skype for Business Server 2019 coexistem na mesma organização, eles trabalham perfeitamente com Exchange UM e Caixa postal na Nuvem para garantir que a caixa postal seja entregue corretamente Exchange caixas de correio. Se Exchange UM ou Caixa postal na Nuvem a caixa postal depende se o usuário está localizado no Skype for Business Server 2015 ou Skype for Business Server 2019:

- Se um usuário estiver localizado no Skype for Business Server 2015, Exchange UM processará a mensagem de caixa postal.
- Se um usuário estiver localizado no Skype for Business Server 2019, Caixa postal na Nuvem processará a mensagem de caixa postal.

Independentemente de Exchange UM ou Caixa postal na Nuvem processe a mensagem de caixa postal, a mensagem será armazenada na caixa de correio Exchange do usuário.

Antes de iniciar a migração para Skype for Business Server 2019, lembre-se do seguinte:

- A caixa postal na nuvem não dá suporte a organizações Atendedor Automático ga. Se você quiser que as caixas de correio movidas para o Caixa postal na Nuvem continuem disponíveis por meio do atendimento automático, você precisará manter pelo menos um servidor Exchange 2013 ou Exchange 2016 executando a função ou serviço de UM disponível.
- As chamadas enviadas para a caixa postal serão transferidas para Caixa postal na Nuvem onde serão gravadas. Depois que a chamada terminar, a mensagem de caixa postal será enviada para a caixa de correio do destinatário no servidor Exchange local. Você precisa levar esse tráfego de voz em consideração ao determinar se sua conectividade com a Internet é suficiente para dar suporte a Caixa postal na Nuvem.

Aqui estão as etapas de alto nível para concluir essa migração.

1. Instale e configure Skype for Business Server 2019 em um novo servidor.
2. Atualize sua configuração de implantação híbrida para incluir o novo Skype for Business 2019.
3. Mova os usuários do servidor Skype for Business 2015 para o servidor Skype for Business 2019.
4. De definir a política de caixa postal hospedada para cada usuário movido para Skype for Business Server 2019 para usar Caixa postal na Nuvem.
5. Desative seus servidores Skype for Business 2015 depois que o último usuário tiver sido movido para fora deles.

    > [!IMPORTANT]
    > Se você depender de um atendente automático, mantenha pelo menos um Exchange 2013 ou Exchange 2016 em execução e disponível.
