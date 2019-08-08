---
title: Planejar a migração do Skype for Business Server e do Exchange Server
ms.reviewer: ''
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.prod: skype-for-business-itpro
description: Este tópico aborda o que você precisa considerar ao decidir migrar suas implantações existentes do Skype for Business Server ou do Exchange Server para a versão mais recente ou para o Skype for Business online ou o Exchange Online.
ms.openlocfilehash: 864a777c1fcb483df7f3779e9b105c1af551748e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237466"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>Planejar a migração do Skype for Business Server e do Exchange Server

Este tópico aborda o que você precisa considerar ao decidir migrar suas implantações existentes do Skype for Business Server ou do Exchange Server para a versão mais recente ou para o Skype for Business online ou o Exchange Online. O que você pode migrar e, quando, depende muito do que você já configurou em sua organização. Alguns recursos, como o atendedor automático da organização, não estão disponíveis na disponibilidade geral (GA), mas serão disponibilizados posteriormente em 2018.

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Alterações de recursos no Exchange 2019 e no Skype for Business Server 2019

Com o Exchange 2019 e o Skype for Business Server 2019, estamos fazendo algumas alterações nos recursos com suporte.

### <a name="unified-messaging-support-in-exchange-2019"></a>Suporte a Unificação de mensagens no Exchange 2019

A Unificação de mensagens (UM) foi preterida no Exchange 2019. Isso significa que o Exchange 2019 não oferece mais os seguintes recursos:

- Caixa postal
- Atendedor automático

Se você implantou a função de UM no Exchange 2013 ou o serviço de UM no Exchange 2016 e deseja atualizar para o Exchange 2019, você precisará migrar a caixa postal para o serviço de caixa postal do Microsoft Cloud no Office 365. Se você quiser migrar sua caixa postal para a caixa postal em nuvem, confira a seção [Exchange 2013/exchange 2016 e Skype for business 2015 para o exchange 2019 e Skype for business 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019) abaixo.
> [!IMPORTANT]
> Se os usuários de seus servidores do Exchange 2013 ou do Exchange 2016 tiverem caixas de correio habilitadas para a UM, não os mova para o Exchange 2019 antes de atualizar seus servidores do Skype for Business para o Skype for Business Server 2019 e mover os usuários para eles para evitar uma interrupção de mensagem de voz.

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Suporte de PBX no Exchange 2019 e no Skype for Business Server 2019

A caixa postal na nuvem não fornece funcionalidade de mensagens de voz para trocas de filiais (PBXs) privadas. Se você estiver usando a Unificação de mensagens do Exchange Server para PBXs e quiser atualizar para o Exchange Server 2019, será necessário adotar uma das três opções listadas na nova data de postagem do blog [para descontinuação do suporte para controladores de borda de sessão no Exchange Unificação de mensagens online](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/) no [blog da equipe do Exchange](https://blogs.technet.microsoft.com/exchange/).

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>Suporte a UM do Exchange Online no Skype for Business Server 2019

Com o Skype for Business Server 2019, estamos migrando da UM do Exchange Online para a caixa postal na nuvem. Quando um usuário for movido para um servidor do Skype for Business 2019, ele começará automaticamente a usar a caixa postal na nuvem quando configurado para caixa postal hospedada. Se você estiver usando a UM do Exchange Online, não será necessário fazer nada além de mover um usuário para o Skype for Business Server 2019 para começar a usar a caixa postal na nuvem. No entanto, há algumas alterações à funcionalidade que você precisa ter em mente:

- O atendedor automático organizacional (o substituto do atendedor automático da UM do Exchange Online) não está disponível no GA, mas estará disponível posteriormente no 2018.
- As configurações de caixa postal do usuário no Outlook na Web não se aplicam à caixa postal na nuvem.

## <a name="on-premises-um-migration-scenarios"></a>Cenários de migração de UM no local

Oferecemos suporte para os seguintes cenários que permitirão a migração de usuários para o Exchange 2019 e para a caixa postal na nuvem. Mais tarde, no 2018 suportaremos cenários adicionais que permitirão a migração de versões adicionais do Exchange e do Skype for Business Server. Também forneceremos recursos adicionais, como atendedor automático da organização.

- Exchange 2013/Exchange 2016 e Skype for Business Server 2015 para o Exchange 2019 e Skype for Business Server 2019
- Skype for Business Server 2015 para o Skype for Business Server 2019 com o Exchange 2013/Exchange 2016

Os cenários a seguir exigem que nenhuma configuração de PBX ou de SBC exista como parte da sua implantação atual e pressuponha que você tem a UM configurada em seus servidores locais do Exchange. Cada uma dessas soluções também pressupõe que você tenha decidido configurar uma implantação híbrida entre seus servidores do Skype for Business no local e o Office 365. Para obter mais informações sobre as implantações híbridas do Skype for Business, consulte [Plan Hybrid Connectivity](plan-hybrid-connectivity.md).

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 e Skype for Business 2015 para o Exchange 2019 e Skype for Business 2019

Neste cenário, você deseja migrar seus servidores existentes do Exchange 2013, Exchange 2016 e Skype for Business 2015 para o Exchange 2019 e o Skype for Business 2019.

Como mencionado anteriormente neste tópico, o Exchange 2019 não inclui mais o serviço de UM. Isso significa que, para todas as caixas de correio que você deseja mover para o Exchange 2019, você precisa usar a caixa postal na nuvem para substituir a funcionalidade fornecida pelo serviço UM. Quando você configura o Skype for Business Server 2019 e uma implantação híbrida entre ele e o Office 365, a caixa postal em nuvem substitui esses serviços de caixa postal do Exchange.

A ordem na qual você move os usuários para o Exchange 2019 e o Skype for Business Server 2019 é fundamental para garantir que a funcionalidade de caixa postal permaneça disponível para todos os usuários. Onde a caixa postal é processada também é determinada pelo local em que as caixas de correio e usuários do Exchange e do Skype for Business estão localizadas. Confira a tabela a seguir para ver quais combinações de Exchange e Skype for Business Server são suportadas e onde a caixa postal é processada.

| Caixa de correio localizada em:            | Usuário localizado no Skype for Business Server 2015 | Usuário localizado no Skype for Business Server 2019  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | UM do Exchange                             | UM do Exchange                              |
| Exchange 2019                  | Sem suporte                           | Caixa postal em nuvem                          |

Antes de iniciar a migração para o Skype for Business Server 2019 e o Exchange 2019, lembre-se do seguinte:

- A caixa postal em nuvem não suporta atendedor automático organizacional no GA. Se quiser que as caixas de correio movidas para a caixa postal em nuvem continuem disponíveis por meio do atendedor automático, você precisará manter pelo menos um servidor do Exchange 2013 ou do Exchange 2016 executando o serviço ou a função de UM disponível.
- Você precisa configurar pelo menos um servidor do Skype for Business 2019 **e** mover os usuários para esse servidor antes de mover suas caixas de correio para o Exchange 2019. Se isso não for feito, as caixas de correio não poderão receber mensagens de voz.
- As chamadas enviadas para a caixa postal serão transferidas para a caixa postal em nuvem onde serão registradas. Após o término da chamada, a mensagem de voz será enviada para a caixa de correio do destinatário no servidor local do Exchange 2019. Você precisa fazer esse tráfego de voz em consideração ao determinar se sua conectividade com a Internet é suficiente para suportar a caixa postal na nuvem.

Aqui estão as etapas de alto nível para concluir a migração.

1. Instale e configure o Skype for Business Server 2019 em um novo servidor.
2. Atualize sua configuração de implantação híbrida para incluir o novo servidor do Skype for Business 2019.
3. Instale e configure o Exchange Server 2019 em um novo servidor.
4. Mova os usuários do seu servidor do Skype for Business 2015 para o servidor do Skype for Business 2019.
5. Defina a política de caixa postal hospedada para cada usuário movido para o Skype for Business Server 2019 para usar a caixa postal na nuvem.
6. Mova as caixas de correio do seu servidor Exchange 2013 ou Exchange 2016 para o servidor do Exchange 2019.
7. Encerre seus servidores do Skype for Business 2015 depois que o último usuário tiver sido movido para fora deles.
8. Encerre seus servidores do Exchange 2013 ou do Exchange 2016 após a última caixa de correio ser movida para fora deles.

    > [!IMPORTANT]
    > Se você depender de um atendedor automático, mantenha pelo menos um Exchange 2013 ou o Exchange 2016 em execução e disponível.

### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>Skype for Business Server 2015 para o Skype for Business Server 2019 com o Exchange 2013/Exchange 2016

Neste cenário, você deseja migrar seu servidor existente do Skype for Business 2015 para o Skype for Business Server 2019, mas permanecer no Exchange 2013 ou no Exchange 2016.

Quando o Skype for Business Server 2015 e o Skype for Business Server 2019 coexistem na mesma organização, eles funcionam perfeitamente com o UM do Exchange e caixa postal na nuvem para garantir que a caixa postal seja entregue corretamente às caixas de correio do Exchange. Se o Exchange ou a caixa postal em nuvem processa o correio de voz depende do fato de o usuário estar localizado no Skype for Business Server 2015 ou no Skype for Business Server 2019:

- Se um usuário estiver localizado no Skype for Business Server 2015, o UM do Exchange processará a mensagem de caixa postal.
- Se um usuário estiver localizado no Skype for Business Server 2019, a caixa postal em nuvem processará a mensagem de caixa postal.

Independentemente de a UM ou a caixa postal do Exchange processar a mensagem de caixa postal, a mensagem será armazenada na caixa de correio do Exchange do usuário.

Antes de iniciar a migração para o Skype for Business Server 2019, lembre-se do seguinte:

- A caixa postal em nuvem não suporta atendedor automático organizacional no GA. Se quiser que as caixas de correio movidas para a caixa postal em nuvem continuem disponíveis por meio do atendedor automático, você precisará manter pelo menos um servidor do Exchange 2013 ou do Exchange 2016 executando o serviço ou a função de UM disponível.
- As chamadas enviadas para a caixa postal serão transferidas para a caixa postal em nuvem onde serão registradas. Após o término da chamada, a mensagem de voz será enviada para a caixa de correio do destinatário no servidor Exchange local. Você precisa fazer esse tráfego de voz em consideração ao determinar se sua conectividade com a Internet é suficiente para suportar a caixa postal na nuvem.

Aqui estão as etapas de alto nível para concluir a migração.

1. Instale e configure o Skype for Business Server 2019 em um novo servidor.
2. Atualize sua configuração de implantação híbrida para incluir o novo servidor do Skype for Business 2019.
3. Mova os usuários do seu servidor do Skype for Business 2015 para o servidor do Skype for Business 2019.
4. Defina a política de caixa postal hospedada para cada usuário movido para o Skype for Business Server 2019 para usar a caixa postal na nuvem.
5. Encerre seus servidores do Skype for Business 2015 depois que o último usuário tiver sido movido para fora deles.

    > [!IMPORTANT]
    > Se você depender de um atendedor automático, mantenha pelo menos um Exchange 2013 ou o Exchange 2016 em execução e disponível.
