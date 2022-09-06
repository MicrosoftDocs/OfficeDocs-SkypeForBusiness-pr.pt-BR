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
description: Este tópico aborda o que você precisa considerar ao decidir migrar suas implantações existentes do Skype for Business Server ou Exchange Server para a versão mais recente ou para o Skype for Business Online ou Exchange Online.
ms.openlocfilehash: ace5151a9a1a910b12b7cba36340bd00f2e96874
ms.sourcegitcommit: 6b4dad9cea8fdad74c493ef62b085dbb9957235d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67486986"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>Plano de migração para o Skype for Business Server e Exchange Server

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Este tópico aborda o que você precisa considerar ao decidir migrar suas implantações Skype for Business Server ou Exchange Server existentes para Exchange Online. O que você pode migrar e quando depende muito do que você já configurou em sua organização.

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Alterações de recursos no Exchange 2019 e Skype for Business Server 2019

Com o Exchange 2019 Skype for Business Server 2019, estamos fazendo algumas alterações nos recursos aos quais damos suporte.

### <a name="unified-messaging-support-in-exchange-2019"></a>Suporte a Unificação de Mensagens no Exchange 2019

A Unificação de Mensagens (UM) foi preterida no Exchange 2019. Isso significa que o Exchange 2019 não oferece mais os seguintes recursos:

- Caixa postal
- Atendedor automático

Se você implantou a função um no Exchange 2013 ou no serviço um no Exchange 2016 e deseja atualizar para o Exchange 2019, será necessário migrar sua caixa postal para o serviço Caixa postal na Nuvem da Microsoft no Microsoft 365 ou Office 365. Se você quiser migrar sua caixa postal para o Caixa postal na Nuvem, dê uma olhada na seção [Exchange 2013/Exchange 2016 e Skype for Business 2015 para o Exchange 2019 e Skype for Business 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019) abaixo.
> [!IMPORTANT]
> Se os usuários em seus servidores Exchange 2013 ou Exchange 2016 tiverem caixas de correio habilitadas para UM, não as mova para o Exchange 2019 antes de atualizar seus servidores do Skype for Business para o Skype for Business Server 2019 e mova os usuários para eles para evitar uma interrupção de mensagens de voz.

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Suporte a PBX no Exchange 2019 e Skype for Business Server 2019

Caixa postal na Nuvem não fornece a funcionalidade de mensagens de voz para PBXs (Private Branch Exchanges). Se você estiver usando o Exchange Server Unified Messaging para PBXs e quiser atualizar para o Exchange Server 2019, precisará adotar uma das três opções listadas na postagem no blog Nova data para a descontinuação do suporte para Controladores de Borda de Sessão no [Exchange Online Unified Messaging](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/) no [Blog da Equipe do Exchange](https://blogs.technet.microsoft.com/exchange/).

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>Exchange Online UM no Skype for Business Server 2019

Com Skype for Business Server 2019, estamos mudando de um Exchange Online para Caixa postal na Nuvem. Quando um usuário for movido para um Skype for Business 2019, ele começará a usar automaticamente Caixa postal na Nuvem quando configurado para a caixa postal hospedada. Se você estiver usando o Exchange Online, não precisará fazer nada além de mover um usuário para o Skype for Business Server 2019 para começar a usar o Caixa postal na Nuvem. No entanto, há algumas alterações na funcionalidade que você precisa estar ciente:

- O Atendedor Automático Organizacional é a substituição do atendedor automático Exchange Online UM.
- As configurações de caixa postal do usuário no Outlook na Web não se aplicam Caixa postal na Nuvem.

## <a name="on-premises-um-migration-scenarios"></a>Cenários de migração de UM local

Damos suporte aos seguintes cenários que permitirão que você migre usuários para o Exchange 2019 e para Caixa postal na Nuvem.

- Exchange 2013/Exchange 2016 e Skype for Business Server 2015 para o Exchange 2019 e Skype for Business Server 2019
- Skype for Business Server 2015 a Skype for Business Server 2019 com o Exchange 2013/Exchange 2016

Os cenários a seguir exigem que nenhuma configuração de PBX ou SBC exista como parte da implantação atual e pressuponham que você tenha um UM configurado em seus servidores Exchange locais. Cada uma dessas soluções também pressupõe que você decidiu configurar uma implantação híbrida entre seus servidores Skype for Business locais e o Microsoft 365 ou Office 365. Para obter mais informações sobre Skype for Business implantações híbridas, consulte [Planejar conectividade híbrida](plan-hybrid-connectivity.md).

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 e Skype for Business 2015 para o Exchange 2019 e Skype for Business 2019

Nesse cenário, você deseja migrar seus servidores existentes do Exchange 2013, do Exchange 2016 e do Skype for Business 2015 para o Exchange 2019 e o Skype for Business 2019.

Conforme mencionado anteriormente neste tópico, o Exchange 2019 não inclui mais o serviço de Unificação de Mensagens. Isso significa que, para todas as caixas de correio que você deseja mover para o Exchange 2019, você precisa usar o Caixa postal na Nuvem para substituir a funcionalidade fornecida pelo serviço de UNIFICAÇÃO. Quando você configura o Skype for Business Server 2019 e uma implantação híbrida entre ele e o Microsoft 365 ou Office 365, o Caixa postal na Nuvem substitui esses serviços de caixa postal da UM do Exchange.

A ordem na qual você move usuários para o Exchange 2019 e o Skype for Business Server 2019 é essencial para garantir que a funcionalidade de caixa postal permaneça disponível para todos os usuários. O local em que a caixa postal é processada também é determinado por onde as caixas de correio e Skype for Business exchange e os usuários estão localizados. Dê uma olhada na tabela a seguir para ver quais combinações de exchange e Skype for Business Server são compatíveis e onde a caixa postal é processada.

| Caixa de correio localizada em:            | Usuário localizado no Skype for Business Server 2015 | Usuário localizado no Skype for Business Server 2019  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | UM do Exchange                             | UM do Exchange                              |
| Exchange 2019                  | Sem suporte                           | Caixa Postal em Nuvem                          |

Antes de iniciar a migração para o Skype for Business Server 2019 e o Exchange 2019, lembre-se do seguinte:

- Você precisa configurar pelo menos um servidor Skype for Business 2019 e mover usuários para esse servidor  antes de mover suas caixas de correio para o Exchange 2019. Não fazer isso fará com que essas caixas de correio não recebam mensagens de voz.
- As chamadas enviadas para a caixa postal serão transferidas Caixa postal na Nuvem local em que serão gravadas. Após o fim da chamada, a mensagem de caixa postal será enviada para a caixa de correio do destinatário no servidor exchange 2019 local. Você precisa levar esse tráfego de voz em conta ao determinar se a conectividade com a Internet é suficiente para dar suporte a Caixa postal na Nuvem.

Aqui estão as etapas de alto nível para concluir essa migração.

1. Instale e configure o Skype for Business Server 2019 em um novo servidor.
2. Atualize sua configuração de implantação híbrida para incluir o novo Skype for Business 2019.
3. Instale e configure o Exchange Server 2019 em um novo servidor.
4. Mova os usuários do Skype for Business 2015 para o Skype for Business 2019.
5. Defina a política de caixa postal hospedada para cada usuário movido para Skype for Business Server 2019 para usar Caixa postal na Nuvem.
6. Mova caixas de correio do servidor Exchange 2013 ou Exchange 2016 para o servidor exchange 2019.
7. Descomissione seus Skype for Business 2015 após o último usuário ter sido removido deles.
8. Descomissione seus servidores Exchange 2013 ou Exchange 2016 após a última caixa de correio ter sido removida deles.


### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>Skype for Business Server 2015 a Skype for Business Server 2019 com o Exchange 2013/Exchange 2016

Nesse cenário, você deseja migrar seu servidor Skype for Business 2015 existente para o Skype for Business Server 2019, mas permanecer no Exchange 2013 ou no Exchange 2016.

Quando Skype for Business Server 2015 e Skype for Business Server 2019 coexistem na mesma organização, eles funcionam perfeitamente com a UM e o Caixa postal na Nuvem do Exchange para garantir que a caixa postal seja entregue corretamente às caixas de correio do Exchange. Se a UM ou Caixa postal na Nuvem exchange processa a caixa postal depende se o usuário está localizado no Skype for Business Server 2015 ou Skype for Business Server 2019:

- Se um usuário estiver localizado no Skype for Business Server 2015, o Exchange UM processará a mensagem de caixa postal.
- Se um usuário estiver localizado no Skype for Business Server 2019, Caixa postal na Nuvem processará a mensagem de caixa postal.

Independentemente de o Exchange UM ou Caixa postal na Nuvem processar a mensagem de caixa postal, a mensagem será armazenada na caixa de correio do Exchange do usuário.

Antes de iniciar a migração para o Skype for Business Server 2019, lembre-se do seguinte:

- As chamadas enviadas para a caixa postal serão transferidas Caixa postal na Nuvem local em que serão gravadas. Depois que a chamada for encerrada, a mensagem de caixa postal será enviada para a caixa de correio do destinatário no servidor Exchange local. Você precisa levar esse tráfego de voz em conta ao determinar se a conectividade com a Internet é suficiente para dar suporte a Caixa postal na Nuvem.

Aqui estão as etapas de alto nível para concluir essa migração.

1. Instale e configure o Skype for Business Server 2019 em um novo servidor.
2. Atualize sua configuração de implantação híbrida para incluir o novo Skype for Business 2019.
3. Mova os usuários do Skype for Business 2015 para o Skype for Business 2019.
4. Defina a política de caixa postal hospedada para cada usuário movido para Skype for Business Server 2019 para usar Caixa postal na Nuvem.
5. Descomissione seus Skype for Business 2015 após o último usuário ter sido removido deles.

