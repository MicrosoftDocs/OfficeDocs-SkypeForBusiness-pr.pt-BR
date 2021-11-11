---
title: Práticas recomendadas de segurança do Teams para mensagens mais seguras
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 11/10/2021
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: Uma referência rápida sobre como usar o Teams com segurança, este artigo atua como uma cartilha sobre as práticas recomendadas de segurança geral e dicas para treinar usuários sobre mensagens seguras.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 61ba1607f2999ef56c3176d4ba8ed0aaebb82e50
ms.sourcegitcommit: 115e44f33fc7993f6eb1bc781f83eb02a506e29b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2021
ms.locfileid: "60909673"
---
# <a name="security-best-practices-for-microsoft-teams"></a>Práticas recomendadas de segurança para o Microsoft Teams

A colaboração por meio de mensagens instantâneas e videoconferência permitiu que muitos setores e escolas continuam seu trabalho durante a pandemia. No entanto, a colaboração online em tempo real em uma escala tão ampla também vem com *riscos* que devem ser resolvidos. Caso contrário, pessoas mal-intencionadas aproveitam essa mudança no trabalho e na vida com campanhas de **phishing** e **spam**. A lista de referência numerada neste artigo atua como uma cartilha para segurança geral ao usar o Teams para enviar mensagens a outras pessoas e é diretrizes de treinamento para pessoas novas no Teams ou para qualquer mensagem instantânea, segurança.

Os mesmos riscos de phishing existentes no email existem em aplicativos de colaboração e mensagens instantâneas, de modo que o mesmo reconhecimento do usuário e diretrizes devem ser aplicados para proteger os usuários do Teams.

No nível do usuário, algumas medidas podem ser simples e os usuários devem se sentir capacitados para confiar neles. Os usuários não devem clicar para abrir links de qualquer pessoa que eles não conhecem ou cuja identidade eles não possam verificar de acordo com o artigo [Proteja-se contra phishing](https://support.microsoft.com/en-us/windows/protect-yourself-from-phishing-0c7ea947-ba98-3bd9-7184-430e1f860a44). E para se proteger contra ataques externos, os administradores de locatários podem desabilitar ou desativar a federação corporativa e a interoperabilidade do Teams for Life (TFL) e do Skype, em relação ao [Gerenciar acesso externo (federação) – Microsoft Teams | Microsoft Docs](/microsoftteams/manage-external-access).

O conjunto de recursos de colaboração do Teams permite mensagens, colaboração de arquivos, reuniões, quadros de comunicações e muitas outras oportunidades de conexão. Esses recursos funcionam no Teams for Enterprise, Teams for Life, Skype, Skype for Business, Serviços de Comunicação do Azure (ACS) e muito mais. Isso também significa que é necessário proteger a si mesmo, seus colegas e seus clientes em toda a amplitude dessas funcionalidades. Aqui, novamente, cada usuário deve ser capacitado a tomar a decisão mais segura para si mesmo, seus colegas e seus clientes.

## <a name="just-as-with-email-online-safety-must-be-practiced-in-microsoft-teams-messaging"></a>Assim como com o email, a segurança online deve ser executada no sistema de mensagens do Microsoft Teams

As medidas de segurança padrão devem ser instaladas enquanto trabalham no Teams.

1. Esteja atento a contatos e solicitações de reunião de fora da sua organização. A linguagem pode ser bem-significado. E alguns podem significar danos em segredo.
2. Se você não reconhecer o remetente, poderá verificar a lista de endereços global conhecida de sua empresa quanto à identidade e escalonar as comunicações que não pode verificar para um nível mais alto para tratamento. Em caso de dúvida, não interaja com usuários desconhecidos e não verificados.
3. Se você receber um link ou arquivo de uma pessoa desconhecida, não clique nele. Mais uma vez, use sua melhor avaliação para seu próprio bem como para a segurança de outros usuários, bem como para seus clientes.
4. Se uma navegação de link clicado o encontrar em uma página de links seguros em que você está bloqueado para navegação, não tente contornar essa página (o mesmo vale para qualquer anexo clicado que possa terminar em vermelho, bloqueando a página de anexos seguros). Se você souber e confiar no site de destino, relate o problema à Microsoft e a quem quer que o encaminhe para lá. Mas há muitos motivos para chegar a uma página de bloqueio, e sinalizadores vermelhos devem ser considerados, em vez de contornados.
5. Nunca forneça informações pessoais a solicitações não solicitadas. Isso também é um risco à segurança pessoal. Detalhes tão simples quanto seu aniversário podem ser aproveitados por invasores.
6. Verifique seus links em busca de ortografia ruim, dígitos adicionados ou caracteres estranhos. Você pode estar esperando um link para `www.litware.com/strategies/Metricsbreakout.xlsx`, mas descobre que o endereço se parece com `www.litwre.com`, `www.litwarecom.com`, ou até mesmo `www.litwαre.com`. Se você não reconhecer o link, seja suspeito. O endereço `www.litware.com` não é o mesmo que `www.litware2021.com`.

É importante manter sua vigilância e não assumir sua segurança, e a segurança daqueles com quem você trabalha de forma leve ou concedida. Como usuários individuais, você sempre deve se sentir capacitado para proteger a si mesmo e seus colegas e clientes por meio da verificação antes de confiar.

Por fim, também é fundamental reconhecer que todos cometeram erros. Os usuários podem ser propensos a clicar quando estão com problemas, por exemplo, ou quando estão cansados. Os administradores devem garantir que os recursos para escalonar cliques de link de problema e outros incidentes de segurança sejam claramente conhecidos pelos usuários em sua organização, para que, se um erro for feito, o usuário tenha reacionado e outras ações de segurança possam ser executadas.

> [!TIP]
> Verifique o cartão de perfil de qualquer contato que você não tenha certeza, especialmente se o email for externo à sua empresa (por exemplo, uma conta que termina em *@litware.com* se sua organização não for *Litware*). Um usuário pode verificar se as pessoas que não conhecem são Convidados bem-vindos a uma reunião verificando o cartão de perfil para **(CONVIDADO)**. Os convidados são expressamente convidados a participar.