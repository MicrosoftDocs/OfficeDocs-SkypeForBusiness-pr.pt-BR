---
title: Noções básicas sobre as recomendações de progresso de leitura
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Saiba como os dados do Insights são usados no Progresso da Leitura para ajudar a melhorar a proficiência de leitura dos alunos.
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-edu
appliesto:
- Microsoft Teams
ms.openlocfilehash: 30a98c9ccda13635a6c3fccaae41e8869b8cfce5
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2022
ms.locfileid: "67157869"
---
# <a name="understand-insights-for-reading-progress-recommendations"></a>Noções básicas sobre as recomendações de progresso de leitura

Este artigo destina-se a administradores de TI educacionais que desejam entender como os dados do Insights são usados para recomendações de Progresso de Leitura.

O Insights permite que os educadores acompanhem a fluência de leitura de seus alunos usando o Progresso da Leitura, uma ferramenta que registra os alunos lendo em voz alta e detecta automaticamente erros.

O Progresso da Leitura fornece os seguintes tipos de atribuições de desafio de leitura:

- **Palavras contextuais**: pratique palavras recomendadas com base nas palavras que os alunos pronunciam incorretamente em tarefas anteriores de Progresso de Leitura.
- **Palavras correlacionadas**: pratique palavras recomendadas com base em erros comuns aos alunos com o mesmo tipo de desafios de leitura.

Para obter diretrizes para educadores sobre como usar Insights para Progresso de Leitura, consulte [Criar atribuições de desafio de Progresso de Leitura com Insights](https://support.microsoft.com/topic/c2f8f4c0-69d5-4302-b3a5-ee4dfb7a8ffe).

## <a name="how-does-microsoft-recommend-correlated-words"></a>Como a Microsoft recomenda palavras correlacionadas?

Palavras correlacionadas são palavras personalizadas e recomendadas que o Insights para Educação identificou como desafiadora para outros alunos que compartilham padrões de leitura semelhantes.

As palavras correlacionadas são baseadas em uma técnica de aprendizado de máquina chamada **filtragem colaborativa**.

- O Insights analisa os dados de leitura dos alunos em classes que compartilham sua área geográfica e idioma para identificar clusters de palavras que são desafiadoras para os alunos.

- Dado um conjunto de palavras desafiadoras, o Insights também identifica clusters semelhantes e os usa para recomendar outras palavras aos alunos para a prática direcionada.

## <a name="does-microsoft-keep-students-data-private-and-secure"></a>A Microsoft mantém os dados dos alunos privados e seguros?

A Microsoft está comprometida em usar dados de forma responsável e ética.

Aqui estão algumas das medidas tomadas para criar esse recurso:

- As análises de dados dos alunos são criadas de maneira olhos-off, o que significa que a Microsoft não tem acesso aos dados de leitura dos alunos, apenas aos resultados da análise.

- Os administradores de locatários podem recusar o processo de análise de dados desativando a alternância De [inferências avançadas](class-insights.md#turn-on-and-off-advanced-inferences-in-insights).

- Palavras inadequadas são filtradas das listas de recomendações **de palavras** correlacionadas. Isso é feito por meio de uma combinação de técnicas de ciência de dados e bloqueio de palavras problemáticas conhecidas. No entanto, esse processo não é uma prova de erro. Os educadores devem examinar as recomendações.

## <a name="what-are-the-limitations-of-insights-word-recommendations"></a>Quais são as limitações das recomendações de palavras do Insights?

- Atualmente, há suporte para recomendações do Word para o Progresso da [Leitura nesses idiomas](https://support.microsoft.com/topic/getting-started-with-reading-progress-in-teams-7617c11c-d685-4cb7-8b75-3917b297c407#ID0EDD=Supported_Languages).

- Palavras correlacionadas são apresentadas apenas em classes com pelo menos cinco alunos que tenham enviado tarefas de Progresso de Leitura.

- O Insights pode não recomendar novas palavras em casos em que não há alunos com padrões de erro semelhantes, mas não idênticos.
