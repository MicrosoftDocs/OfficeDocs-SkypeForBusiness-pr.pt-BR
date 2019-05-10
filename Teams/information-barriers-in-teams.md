---
title: Barreiras de informações no Microsoft Teams preview
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/30/2019
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
ms.reviewer: vikramju
description: Saiba mais sobre as barreiras de informações e como eles afetam as equipes.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 71c547ac13f63c9357dfb6e8a0cbe34d748646d3
ms.sourcegitcommit: b072148ea13f4d4f6035204a48bedd287fb90ebd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2019
ms.locfileid: "33827784"
---
# <a name="information-barriers-in-microsoft-teams-preview"></a>Barreiras de informações no Microsoft Teams preview

> [!INCLUDE [Preview feature](includes/preview-feature.md)]

Barreiras de informações são diretivas que um administrador pode configurar para impedir o indivíduos ou grupos de se comunicar entre si. Isso é útil se, por exemplo, um departamento está manipulando informações que não devem ser compartilhadas com outros departamentos ou um grupo precisa ser impedidos de se comunicar com qualquer contatos externos.

> [!NOTE]
> - Não não possível criar grupos de barreira de informações entre locatários.
> - Usando bots para adicionar usuários, não há suporte para a versão 1.

Políticas de barreira informações também impedem pesquisas e descoberta. Isso significa que se você tentar se comunicar com alguém, com que você não deve estar comunicando, você não encontrará que o usuário no seletor de pessoas.

## <a name="background"></a>Plano de fundo

O principal motivador para informações barreiras proveniente do setor de serviços financeiros. A autoridade de regulamentação setor financeiro ([FINRA]( http://www.finra.org/)) revisa barreiras da informação e conflitos de interesses dentro de empresas de membro e fornece orientação sobre como gerenciar esses conflitos (FINRA 2241, [Aviso de regulamentação do débito Research 31 de 15](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf).  

## <a name="when-should-i-use-information-barriers"></a>Quando devo usar barreiras da informação?

Você pode querer usar barreiras da informação em situações como essas:

- Uma equipe deve ser impedida de comunicação ou compartilhamento de dados com uma determinada outra equipe.
- Uma equipe não deve se comunicar ou compartilhar dados com alguém de fora da equipe.

O serviço de avaliação de diretiva de barreira informações determina se uma comunicação está em conformidade com as políticas de barreira de informações. 

## <a name="managing-information-barrier-policies"></a>Gerenciando políticas de barreira de informações

Políticas de barreira de informações são gerenciadas com segurança & cmdlets do PowerShell do Centro de conformidade (SCC). Para obter mais informações sobre como usar esses cmdlets, [Inscreva-se aqui](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR1UzUQTEgHVPtD9W5uih2OlUMEwwUzhJSktIMUw2SDJJOE5FT1lTVzVTSS4u).

> [!IMPORTANT]
> Antes que você configurou ou define políticas, **você deve habilitar a pesquisa de diretório com escopo em equipes da Microsoft**. Aguarde pelo menos 24 horas após habilitar a pesquisa de diretório com escopo antes de configurar ou definir políticas para as barreiras de informações.

## <a name="information-barriers-administrator-role"></a>Função de administrador de barreiras de informações

A função de administrador de barreiras informações é responsável por gerenciar políticas de barreira de informações. Para obter mais informações sobre essa função e participem de visualização, [Inscreva-se aqui](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR1UzUQTEgHVPtD9W5uih2OlUMEwwUzhJSktIMUw2SDJJOE5FT1lTVzVTSS4u).

## <a name="when-are-information-barrier-policies-checked"></a>Quando as políticas de barreira informações são verificadas?

Políticas de barreira informações são verificadas quando os eventos de equipes a seguir ocorrerão:

- **Membros são adicionados para uma equipe** - sempre que você adicionar um usuário para uma equipe, a diretiva do usuário deve ser avaliada contra as políticas de barreira informações de outros membros da equipe. Depois que o usuário é adicionado com êxito, o usuário pode executar todas as funções na equipe de sem verificações adicionais. Se a diretiva do usuário impede que eles sejam adicionados à equipe, o usuário não serão exibidas na pesquisa.
- **Um novo chat é solicitado** - sempre que um novo chat é solicitado entre dois ou mais usuários, o bate-papo é avaliado para certificar-se de que ele não está violar quaisquer políticas de barreira informações. Se a conversa violar uma política de barreira informações, então a conversa não será iniciada e uma mensagem de erro é exibida.
- **Um usuário está convidado para ingressar em uma reunião** - quando um usuário está convidado para ingressar em uma reunião, a diretiva do usuário é avaliada contra as políticas de outros membros da equipe e se houver uma violação, o usuário não poderão ingressar na reunião e verá uma mensagem de erro.
- **Que uma tela é compartilhada entre dois ou mais usuários** - sempre que uma tela é compartilhado entre dois ou mais usuários, o compartilhamento de tela deve ser avaliado para certificar-se de que ele não viola as políticas de barreira informações de outros usuários. Se uma política de barreira informações for violada, o compartilhamento de tela não será possível e uma mensagem de erro será exibida.
- **Um usuário faz uma chamada telefônica (VOIP) em equipes** - sempre que uma chamada de voz é iniciada por um usuário para outro usuário ou grupo de usuários, a chamada é avaliada para certificar-se de que ele não viola as políticas de barreira informações dos membros da equipe oher. Se houver qualquer violação, a chamada de voz está bloqueada.

## <a name="what-happens-to-existing-chat-threads-when-a-policy-is-changed"></a>O que acontece com threads de bate-papo existentes quando uma política for alterada?

Quando o administrador de política de barreira informações faz alterações à política ou uma alteração na diretiva é ativado em vigor por causa do trabalho de um usuário alterar ou uma razão semelhante, o serviço de avaliação de diretiva de barreira informações automaticamente pesquisará os membros para garantir que membros da equipe não são violar quaisquer políticas. 

Se houver um chat existente ou outras comunicações entre usuários e uma nova política estiver definida ou uma política existente é alterada, o serviço avalia as comunicações existentes para certificar-se de que eles não são "inviabilizados" (não permitido): 

- **bate-papo de 1:1** - se a comunicação entre os dois usuários não mais é permitida (se uma diretiva de bloqueio de comunicação é aplicada a um ou ambos os usuários), ainda mais a comunicação é bloqueada e a conversa de bate-papo se tornará somente leitura.
- **O chat de grupo** - se a comunicação de um usuário ao grupo não é mais permitida (por exemplo, se um usuário altera trabalhos), juntamente com os outros usuários que violam a política de usuário pode ser removido do chat de grupo e não será mais nenhuma comunicação com o grupo permitido. O usuário ainda pode ver conversas antigas (que serão somente leitura), mas não será possível ver ou participar de qualquer novas conversas com o grupo. Se a política de nova ou alterada, impedindo a comunicação será aplicada a mais de um usuário, os usuários que são afetados pela diretiva podem ser removidos do chat de grupo. Eles ainda poderão ver conversas antigas. 
- **Equipe** - todos os usuários que foram removidos do grupo serão removidos da equipe do e não será possível ver ou participar de conversas novas ou existentes.

## <a name="required-licenses-and-permissions"></a>Permissões e licenças necessárias

Atualmente, os recursos de barreira informações estão no modo de visualização público. Quando esses recursos estão disponíveis em geral, eles serão incluídos no inscrições, tais como:

- Microsoft 365 E5
- Office 365 E5
- O Office 365 avançadas de conformidade
- Microsoft 365 E5 conformidade

Para obter mais detalhes, incluindo planos e preços, consulte [Soluções de conformidade](https://products.office.com/business/security-and-compliance/compliance-solutions?rtc=1).
