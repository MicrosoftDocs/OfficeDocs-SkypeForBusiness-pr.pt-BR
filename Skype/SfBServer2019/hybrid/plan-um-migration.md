---
title: Planeje Skype para migração Business Server e o Exchange Server
author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.prod: skypeforbusiness-server-itpro
description: Este tópico aborda o que você precisa considerar ao decidir migrar seu Skype existente para implantações Business Server ou o Exchange Server para a versão mais recente ou Skype para Business Online ou Exchange Online.
ms.openlocfilehash: 25d0e275110df57747679efec46a77571259a3d4
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027253"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>Planeje Skype para migração Business Server e o Exchange Server

[!INCLUDE [disclaimer](../disclaimer.md)]

Este tópico aborda o que você precisa considerar ao decidir migrar seu Skype existente para implantações Business Server ou o Exchange Server para a versão mais recente ou Skype para Business Online ou Exchange Online. O que você pode migrar e quando, depende muito o que você já tem configurou na sua organização. No modo de visualização, estamos direcionando esforços em dar suporte a alguns cenários específicos, com cenários adicionais se tornando disponível em disponibilidade geral (GA).

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Alterações no Exchange 2019 e Skype de recursos de Business Server 2019

Com o Exchange 2019 e Skype para Business Server 2019, estamos fazendo algumas alterações aos recursos que suportamos.

### <a name="unified-messaging-support-in-exchange-2019"></a>Unified Messaging suporte no Exchange 2019

Unificação de mensagens (UM) foi preterido no Exchange 2019. Isso significa que o Exchange 2019 não mais oferece os seguintes recursos:

- Caixa postal
- Atendedor Automático

Se você implantou a função de Unificação de mensagens no Exchange 2013 ou o serviço de Unificação de mensagens no Exchange 2016 e você deseja atualizar para o Exchange 2019, você precisará migrar sua caixa postal para o serviço de correio de voz do Microsoft Cloud no Office 365. Se você quiser migrar sua caixa postal para a caixa postal de nuvem, dê uma olhada na seção [Exchange 2013/Exchange 2016 e Skype para negócios 2015 2019 do Exchange e do Skype para negócios 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019) abaixo.
> [!IMPORTANT]
> Se os usuários em seus servidores Exchange 2013 ou 2016 do Exchange tiverem habilitado caixas de correio, não movê-los para Exchange 2019 antes de atualizar seu Skype para servidores de negócios para Skype para Business Server 2019 e mover os usuários a eles para evitar uma interrupção de mensagens de voz.

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Suporte de PBX no Exchange 2019 e Skype para Business Server 2019

Caixa postal de nuvem não fornece funcionalidade para privadas de comutação (PBXs) de mensagens de voz. Se você estiver usando a Unificação de mensagens do Exchange Server para PBXs e você deseja atualizar para o Exchange Server 2019, você precisará adotar uma das três opções listadas na postagem do blog [nova data de suporte para controladores de borda de sessão foi descontinuado no Exchange Unificação de mensagens online](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/) no [Blog da equipe do Exchange](https://blogs.technet.microsoft.com/exchange/).

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>Exchange Online UM suporte no Skype para Business Server 2019

Com Skype para Business Server 2019, estamos passando UM do Exchange Online para a caixa postal de nuvem. Quando um usuário é movido para um Skype para 2019 Business server, eles começará automaticamente usando a caixa postal de nuvem quando configurado para caixa postal hospedada. Se você estiver usando atualmente Online UM do Exchange, você não precisa fazer algo diferente de mover um usuário Skype para o servidor de negócios 2019 começar a usar a caixa postal de nuvem. No entanto, há algumas alterações de funcionalidade que você precisa estar ciente:

- Para visualizar, organizacional atendente automático (o substituto do atendedor automático no Exchange Online UM) não está disponível. Atendedor automático da organizacional estará disponível no mercado.
- As configurações de caixa postal do usuário do Outlook na Web não se aplicam ao correio de voz de nuvem.

## <a name="on-premises-um-migration-scenarios"></a>Cenários de migração de UM local

No modo de visualização, podemos está apoiando os seguintes cenários que permitem que você migrar usuários para o Exchange 2019 e para a caixa postal de nuvem. No GA vai suportamos cenários adicionais que permitirá que você a migrar de versões adicionais do Exchange e Skype para Business server. Também forneceremos recursos adicionais, como o atendedor automático de organizacionais.

- Exchange 2013/Exchange 2016 e Skype para Business Server 2015 para Exchange 2019 e Skype para Business Server 2019
- Skype para Business Server 2015 para Skype para Business Server 2019 com Exchange 2013/Exchange 2016

Os cenários a seguir exigem que as configurações de PBX ou SBC existirem como parte da sua implantação atual e pressupõem que você tenha configurada em seus servidores do Exchange no local de Unificação de mensagens. Cada uma dessas soluções também pressupõe que você decidiu configurar uma implantação híbrida entre Skype seu local para os servidores de negócios e do Office 365. Para obter mais informações sobre Skype para implantações híbridas de negócios, consulte [Skype para soluções híbridas de negócios](hybrid-solutions.md).

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 e Skype para negócios 2015 para Exchange 2019 e Skype para negócios 2019

Neste cenário, você deseja migrar seus existente do Exchange 2013, o Exchange 2016 e o Skype para que servidores corporativos 2015 2019 do Exchange e o Skype para negócios 2019.

Conforme mencionado anteriormente neste tópico, o Exchange 2019 inclui o serviço de Unificação de mensagens não são mais. Isso significa que, para qualquer caixa de correio que você deseja mover para o Exchange 2019, você precisa usar a caixa postal de nuvem para substituir a funcionalidade fornecida pelo serviço de Unificação de mensagens. Quando você configura Skype para Business Server 2019 e uma implantação híbrida entre ele e o Office 365, caixa postal de nuvem substitui esses serviços de caixa postal de UM do Exchange.

A ordem na qual mover usuários para o Exchange 2019 e Skype para Business Server 2019 é crucial para garantir que a funcionalidade de caixa postal permanece disponível para todos os usuários. Onde é processada a caixa postal também é determinada pelo onde o Exchange e Skype para caixas de correio de negócios e usuários que estão localizados. Dê uma olhada na tabela a seguir para ver quais combinações do Exchange e do Skype para Business Server são suportadas e onde é processada a caixa postal.

| Caixa de correio localizada em:            | Usuário localizado na Skype para Business Server 2015 | Usuário localizado na Skype para Business Server 2019  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | UM do Exchange                             | Caixa postal de nuvem                          |
| Exchange 2019                  | Não suportado                           | Caixa postal de nuvem                          |

Antes de iniciar a migração para o Skype para Business Server 2019 e Exchange 2019, lembre-se do seguinte:

- Caixa postal de nuvem não suporta organizacional atendedor automático na visualização. Se você quiser movidas para a caixa postal de nuvem para continuar a ser disponibilizada pelo atendedor automático de caixas de correio, você precisará manter pelo menos um servidor Exchange 2013 ou Exchange 2016 executando a função de Unificação de mensagens ou o serviço está disponível.
- Você precisará configurar pelo menos um Skype para negócios 2019 server **e** mover usuários para o servidor antes de mover suas caixas de correio para o Exchange 2019. Falha em fazer isso resultará nessas caixas de correio que está sendo capaz de receber mensagens de caixa postal.
- Chamadas enviadas para a caixa postal serão transferidas para a caixa postal de nuvem onde eles serão registrados. Depois que a chamada for encerrada, a mensagem de caixa postal será enviada à caixa de correio do destinatário no servidor Exchange 2019 no local. Você precisa ser esse tráfego de voz analisadas ao determinar se a conectividade com a Internet é suficiente para suportar a caixa postal de nuvem.

Aqui estão as etapas de alto nível para concluir essa migração.

1. Instalar e configurar o Skype para Business Server 2019 em um novo servidor.
2. Atualize sua configuração de implantação híbrida para incluir o novo Skype para negócios 2019 server.
3. Instalar e configurar o Exchange Server 2019 em um novo servidor.
4. Mova usuários de sua Skype para 2015 Business server para sua Skype para negócios 2019 server.
5. Defina a diretiva de caixa postal hospedada para cada usuário movido para Skype para negócios 2019 de servidor usar a caixa postal de nuvem.
6. Mova caixas de correio do seu servidor Exchange 2013 ou Exchange 2016 ao seu servidor Exchange 2019.
7. Encerre sua Skype para servidores de negócios 2015 após o último usuário foi movido fora deles.
8. Encerre seus servidores Exchange 2013 ou Exchange 2016 após a última caixa de correio foi movida fora deles.

    > [!IMPORTANT]
    > Se você confiar em um atendedor automático, mantenha pelo menos um Exchange 2013 ou 2016 do Exchange em execução e disponível.

### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>Skype para Business Server 2015 para Skype para Business Server 2019 com Exchange 2013/Exchange 2016

Neste cenário, você deseja migrar seu Skype existente para o servidor de negócios 2015 para Skype para Business Server 2019, mas permanecem no Exchange 2013 ou 2016 do Exchange.

Quando Skype para Business Server 2015 e Skype para Business Server 2019 coexistirem na mesma organização, funcionem perfeitamente com UM do Exchange e caixa postal de nuvem para garantir que voicemail corretamente é entregue às caixas de correio do Exchange. Se o UM do Exchange ou caixa postal de nuvem processa a caixa postal depende se o usuário está localizado em Skype para Business Server 2015 ou Skype para Business Server 2019:

- Se um usuário estiver localizado em Skype para Business Server 2015, UM do Exchange processará a mensagem de caixa postal.
- Se um usuário estiver localizado em Skype para Business Server 2019, caixa postal de nuvem processará a mensagem de caixa postal.

Independentemente se a UM do Exchange ou caixa postal de nuvem processa a mensagem de caixa postal, a mensagem será armazenada na caixa de correio do Exchange do usuário.

Antes de iniciar a migração para o Skype para Business Server 2019, lembre-se do seguinte:

- Caixa postal de nuvem não suporta organizacional atendedor automático na visualização. Se você quiser movidas para a caixa postal de nuvem para continuar a ser disponibilizada pelo atendedor automático de caixas de correio, você precisará manter pelo menos um servidor Exchange 2013 ou Exchange 2016 executando a função de Unificação de mensagens ou o serviço está disponível.
- Chamadas enviadas para a caixa postal serão transferidas para a caixa postal de nuvem onde eles serão registrados. Depois que a chamada for encerrada, a mensagem de caixa postal será enviada à caixa de correio do destinatário no servidor Exchange local. Você precisa ser esse tráfego de voz analisadas ao determinar se a conectividade com a Internet é suficiente para suportar a caixa postal de nuvem.

Aqui estão as etapas de alto nível para concluir essa migração.

1. Instalar e configurar o Skype para Business Server 2019 em um novo servidor.
2. Atualize sua configuração de implantação híbrida para incluir o novo Skype para negócios 2019 server.
3. Mova usuários de sua Skype para 2015 Business server para sua Skype para negócios 2019 server.
4. Defina a diretiva de caixa postal hospedada para cada usuário movido para Skype para negócios 2019 de servidor usar a caixa postal de nuvem.
5. Encerre sua Skype para servidores de negócios 2015 após o último usuário foi movido fora deles.

    > [!IMPORTANT]
    > Se você confiar em um atendedor automático, mantenha pelo menos um Exchange 2013 ou 2016 do Exchange em execução e disponível.