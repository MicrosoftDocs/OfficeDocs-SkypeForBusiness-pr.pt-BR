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
localization_priority: Normal
ms.prod: skype-for-business-itpro
description: Este tópico aborda o que você precisa considerar ao decidir migrar suas implantações existentes do Skype for Business Server ou do Exchange Server para a versão mais recente ou para o Skype for Business Online ou Exchange Online.
ms.openlocfilehash: cb6d58cf839b6260bc8889817ea568528e4832f4
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359037"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>Plano de migração para o Skype for Business Server e Exchange Server

Este tópico aborda o que você precisa considerar ao decidir migrar suas implantações existentes do Skype for Business Server ou do Exchange Server para o Exchange Online. O que você pode migrar e quando depende muito do que você já está configurando em sua organização.

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Alterações de recursos no Exchange 2019 e no Skype for Business Server 2019

Com o Exchange 2019 e o Skype for Business Server 2019, estamos fazendo algumas alterações nos recursos que suportamos.

### <a name="unified-messaging-support-in-exchange-2019"></a>Suporte à Unificação de Mensagens no Exchange 2019

A Unificação de Mensagens (UM) foi preterida no Exchange 2019. Isso significa que o Exchange 2019 não oferece mais os seguintes recursos:

- Caixa postal
- Auto attendant

Se você implantou a função um no Exchange 2013 ou o serviço de UM no Exchange 2016 e deseja atualizar para o Exchange 2019, você precisará migrar sua caixa postal para o serviço de Caixa Postal do Microsoft Cloud no Microsoft 365 ou Office 365. Se você quiser migrar sua caixa postal para a Caixa Postal na Nuvem, confira a seção [Exchange 2013/Exchange 2016 e Skype for Business 2015 para o Exchange 2019 e o Skype for Business 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019) abaixo.
> [!IMPORTANT]
> Se os usuários em seus servidores Exchange 2013 ou Exchange 2016 têm caixas de correio habilitadas para UM, não mova-as para o Exchange 2019 antes de atualizar seus servidores do Skype for Business para o Skype for Business Server 2019 e mova os usuários para eles para evitar uma paralisação de mensagens de voz.

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Suporte a PBX no Exchange 2019 e no Skype for Business Server 2019

A Caixa Postal na Nuvem não fornece a funcionalidade de mensagens de voz para PBXs (Private Branch Exchanges). Se você estiver usando a Unificação de Mensagens do Exchange Server para PBXs e quiser atualizar para o Exchange Server 2019, precisará adotar uma das três opções listadas na postagem do blog Nova data para descontinuação do suporte para Controladores de Borda de Sessão na Unificação de Mensagens do [Exchange Online](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/) no Blog da Equipe do [Exchange.](https://blogs.technet.microsoft.com/exchange/)

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>Suporte à UM do Exchange Online no Skype for Business Server 2019

Com o Skype for Business Server 2019, estamos mudando da UM do Exchange Online para a Caixa Postal na Nuvem. Quando um usuário é movido para um servidor do Skype for Business 2019, ele começa automaticamente a usar a Caixa Postal na Nuvem quando configurado para caixa postal hospedada. Se você estiver usando a UM do Exchange Online no momento, não precisará fazer nada além de mover um usuário para o Skype for Business Server 2019 para começar a usar a Caixa Postal na Nuvem. No entanto, há algumas alterações na funcionalidade que você precisa estar ciente:

- O Atendente Automático Organizacional é o substituto do atendente automático na UM do Exchange Online.
- As configurações de caixa postal do usuário no Outlook na Web não se aplicam à Caixa Postal na Nuvem.

## <a name="on-premises-um-migration-scenarios"></a>Cenários de migração de UM local

Suportamos os seguintes cenários que permitirão migrar usuários para o Exchange 2019 e para a Caixa Postal na Nuvem.

- Exchange 2013/Exchange 2016 e Skype for Business Server 2015 para Exchange 2019 e Skype for Business Server 2019
- Skype for Business Server 2015 para Skype for Business Server 2019 com Exchange 2013/Exchange 2016

Os cenários a seguir exigem que não existam configurações de PBX ou SBC como parte de sua implantação atual e pressufiram que você tenha a UM configurada em seus servidores locais do Exchange. Cada uma dessas soluções também presume que você decidiu configurar uma implantação híbrida entre seus servidores locais do Skype for Business e o Microsoft 365 ou Office 365. Para obter mais informações sobre implantações híbridas do Skype for Business, consulte [Planejar conectividade híbrida.](plan-hybrid-connectivity.md)

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 e Skype for Business 2015 para Exchange 2019 e Skype for Business 2019

Neste cenário, você deseja migrar seus servidores existentes do Exchange 2013, do Exchange 2016 e do Skype for Business 2015 para o Exchange 2019 e o Skype for Business 2019.

Conforme mencionado anteriormente neste tópico, o Exchange 2019 não inclui mais o serviço de UM. Isso significa que, para todas as caixas de correio que você deseja mover para o Exchange 2019, você precisa usar a Caixa Postal na Nuvem para substituir a funcionalidade que foi fornecida pelo serviço de UM. Quando você configura o Skype for Business Server 2019 e uma implantação híbrida entre ele e o Microsoft 365 ou o Office 365, a Caixa Postal na Nuvem substitui esses serviços de caixa postal da UM do Exchange.

A ordem na qual você move os usuários para o Exchange 2019 e o Skype for Business Server 2019 é fundamental para garantir que a funcionalidade da caixa postal permaneça disponível para todos os usuários. Onde a caixa postal é processada também é determinada por onde as caixas de correio e os usuários do Exchange e do Skype for Business estão localizados. Dê uma olhada na tabela a seguir para ver quais combinações do Exchange e do Skype for Business Server são suportadas e onde a caixa postal é processada.

| Caixa de correio localizada em:            | Usuário localizado no Skype for Business Server 2015 | Usuário localizado no Skype for Business Server 2019  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | UM do Exchange                             | UM do Exchange                              |
| Exchange 2019                  | Sem suporte                           | Caixa Postal em Nuvem                          |

Antes de iniciar a migração para o Skype for Business Server 2019 e o Exchange 2019, lembre-se do seguinte:

- A caixa postal na nuvem não dá suporte ao Atendedor Automático Organizacional no GA. Se quiser que as caixas de correio movidas para a Caixa Postal na Nuvem continuem disponíveis por meio do atendedor automático, você precisará manter pelo menos um servidor exchange 2013 ou Exchange 2016 executando a função ou serviço de UM disponível.
- Você precisa configurar pelo menos um servidor do Skype  for Business 2019 e mover usuários para esse servidor antes de mover suas caixas de correio para o Exchange 2019. Se não fizer isso, essas caixas de correio não poderão receber mensagens de caixa postal.
- As chamadas enviadas para a caixa postal serão transferidas para a Caixa Postal na Nuvem, onde serão gravadas. Após o fim da chamada, a mensagem de caixa postal será enviada para a caixa de correio do destinatário no servidor local do Exchange 2019. Você precisa levar esse tráfego de voz em consideração ao determinar se sua conectividade com a Internet é suficiente para dar suporte à caixa postal na nuvem.

Aqui estão as etapas de alto nível para concluir essa migração.

1. Instale e configure o Skype for Business Server 2019 em um novo servidor.
2. Atualize sua configuração de implantação híbrida para incluir o novo servidor do Skype for Business 2019.
3. Instale e configure o Exchange Server 2019 em um novo servidor.
4. Mova os usuários do seu servidor do Skype for Business 2015 para o seu servidor do Skype for Business 2019.
5. Definir a política de caixa postal hospedada para cada usuário movido para o Skype for Business Server 2019 para usar a Caixa Postal na Nuvem.
6. Mova caixas de correio do seu servidor Exchange 2013 ou Exchange 2016 para seu servidor Exchange 2019.
7. Descomissione seus servidores do Skype for Business 2015 depois que o último usuário tiver sido movido para fora deles.
8. Descomissione seus servidores Exchange 2013 ou Exchange 2016 após a última caixa de correio ter sido movida para fora deles.

    > [!IMPORTANT]
    > Se você depender de um atendente automático, mantenha pelo menos um Exchange 2013 ou Exchange 2016 em execução e disponível.

### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>Skype for Business Server 2015 para Skype for Business Server 2019 com Exchange 2013/Exchange 2016

Neste cenário, você deseja migrar seu servidor skype for Business 2015 existente para o Skype for Business Server 2019, mas permanecer no Exchange 2013 ou Exchange 2016.

Quando o Skype for Business Server 2015 e o Skype for Business Server 2019 coexistem na mesma organização, eles funcionam perfeitamente com a UM do Exchange e a Caixa Postal na Nuvem para garantir que a caixa postal seja entregue corretamente às caixas de correio do Exchange. Se a UM do Exchange ou a Caixa Postal na Nuvem processa a caixa postal depende se o usuário está localizado no Skype for Business Server 2015 ou no Skype for Business Server 2019:

- Se um usuário estiver localizado no Skype for Business Server 2015, a UM do Exchange processará a mensagem de caixa postal.
- Se um usuário estiver localizado no Skype for Business Server 2019, a Caixa Postal na Nuvem processará a mensagem de caixa postal.

Independentemente se a UM do Exchange ou a Caixa Postal na Nuvem processa a mensagem de caixa postal, a mensagem será armazenada na caixa de correio do Exchange do usuário.

Antes de iniciar a migração para o Skype for Business Server 2019, lembre-se do seguinte:

- A caixa postal na nuvem não dá suporte ao Atendedor Automático Organizacional no GA. Se quiser que as caixas de correio movidas para a Caixa Postal na Nuvem continuem disponíveis por meio do atendedor automático, você precisará manter pelo menos um servidor exchange 2013 ou Exchange 2016 executando a função ou serviço de UM disponível.
- As chamadas enviadas para a caixa postal serão transferidas para a Caixa Postal na Nuvem, onde serão gravadas. Após o fim da chamada, a mensagem de caixa postal será enviada para a caixa de correio do destinatário no servidor exchange local. Você precisa levar esse tráfego de voz em consideração ao determinar se sua conectividade com a Internet é suficiente para dar suporte à caixa postal na nuvem.

Aqui estão as etapas de alto nível para concluir essa migração.

1. Instale e configure o Skype for Business Server 2019 em um novo servidor.
2. Atualize sua configuração de implantação híbrida para incluir o novo servidor do Skype for Business 2019.
3. Mova os usuários do seu servidor do Skype for Business 2015 para o seu servidor do Skype for Business 2019.
4. Definir a política de caixa postal hospedada para cada usuário movido para o Skype for Business Server 2019 para usar a Caixa Postal na Nuvem.
5. Descomissione seus servidores do Skype for Business 2015 depois que o último usuário tiver sido movido para fora deles.

    > [!IMPORTANT]
    > Se você depender de um atendente automático, mantenha pelo menos um Exchange 2013 ou Exchange 2016 em execução e disponível.
