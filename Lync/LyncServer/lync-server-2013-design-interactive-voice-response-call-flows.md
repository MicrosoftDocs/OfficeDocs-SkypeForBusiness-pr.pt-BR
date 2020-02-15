---
title: 'Lync Server 2013: projetar fluxos de chamada de resposta interativa de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Design interactive voice response call flows
ms:assetid: f3477f0a-3ad5-4b13-a73c-046aa451db19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413020(v=OCS.15)
ms:contentKeyID: 48185826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff6587c2dc70a638d1db670205fb5bfde452e499
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="design-interactive-voice-response-call-flows-in-lync-server-2013"></a>Projetar fluxos de chamada de resposta interativa de voz no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-25_

É possível usar a resposta de voz interativa (IVR) para obter as informações dos chamadores e enviar a chamada para a fila adequada. Pares de perguntas e respostas determinam a fila a usar. Dependendo da resposta do chamador, o chamador ouve uma pergunta de acompanhamento ou é roteado para a fila adequada. As perguntas IVR e as respostas do chamador são oferecidas para o agente de resposta quando ele ou ela aceitar a chamada. O sistema oferece informações valiosas para o agente de resposta.

<div>

## <a name="overview-of-ivr-features"></a>Visão geral dos recursos do IVR

O aplicativo grupo de resposta oferece recursos de reconhecimento de fala e conversão de texto em fala em 26 idiomas. É possível inserir perguntas IVR usando a conversão texto em fala ou um arquivo wave (.wav) ou Windows Media audio (.wma). Os chamadores podem responder usando a voz ou multifrequência de dois tons (DTMF).

Os fluxos de trabalho interativos suportam até dois níveis de perguntas, com cada pergunta tendo até quatro respostas possíveis. A IVR faz uma pergunta ao chamador e, dependendo da resposta, roteia o chamador para uma fila ou faz uma segunda pergunta. A segunda pergunta também pode ter quatro respostas possíveis. Dependendo da resposta à pergunta de segundo nível, o chamador é roteado para a fila adequada.

<div>


> [!NOTE]  
> Ao projetar fluxos de chamadas usando o Shell de gerenciamento do Lync Server, você pode definir qualquer nível de número de perguntas IVR e qualquer número de respostas. No entanto, para melhor usabilidade do chamador, recomendamos que você não use mais de três níveis de perguntas, com não mais do que cinco respostas cada. Além disso, se você criar um fluxo de chamadas com mais de dois níveis de perguntas com mais de quatro respostas, não será possível editar o fluxo de chamadas usando o painel de controle do Lync Server 2013.



</div>

As perguntas IVR e as respostas do chamador são fornecidas para o agente de resposta quando ele ou ela aceita a chamada.

</div>

<div>

## <a name="working-with-speech-technologies"></a>Trabalhando com tecnologias de fala

Tecnologias de fala, como o reconhecimento de fala e conversão de texto em fala, podem aprimorar a experiência do cliente e permitir que as pessoas acessem informações de forma mais natural e eficaz. No entanto, pode haver casos em que o texto especificado ou a resposta de voz do usuário não é reconhecido corretamente pelo mecanismo de fala. Por exemplo, o símbolo\#"" é traduzido pelo mecanismo de conversão de texto em fala como a palavra "número". Este problema pode ser reduzido pelo seguinte:

  - O mecanismo de fala fornece ao chamador cinco tentativas de responder a pergunta. Se o chamador responder incorretamente (isto é, a resposta não é uma das respostas especificadas) ou não oferecer uma resposta, ele ou ela tem outra chance de responder. O chamador tem cinco tentativas de responder a pergunta antes de ser desconectado. É possível configurar a IVR para reproduzir uma mensagem personalizada após cada erro do chamador. A pergunta é repetida todas as vezes.

  - Para minimizar que o potencial ruído ambiente seja interpretado pelo mecanismo de fala como uma resposta, use respostas mais longas. Por exemplo, as respostas devem ter mais de uma sílaba e devem soar diferente uma da outra.

  - Se suas perguntas possuem respostas de fala e DTMF, configure as respostas de fala com palavras que representam um conceito ao invés da resposta DTMF. Por exemplo, ao invés de usar "Pressione ou fale 1", use "Pressione 1 ou fale faturamento."

  - Após projetar sua IVR, ligue par ao fluxo de trabalho, ouça às solicitações, responda cada uma delas usando a voz e verifique se a IVR soa e se comporta conforme esperado. É possível modificar a IVR para corrigir qualquer problema de interpretação. Após o exemplo anterior, se você precisar fazer referência à \# chave, você pode reconfigurar seu prompt IVR para usar o nome da chave, em vez do \# símbolo. Por exemplo, "Para falar com vendas, pressione a tecla jogo da velha."

</div>

<div>

## <a name="ivr-design-examples"></a>Exemplos de design de IVR

As seções a seguir contêm exemplos de diferentes cenários de IVR e pares de perguntas e respostas.

<div>

## <a name="ivr-with-one-level-of-questions"></a>IVR com um nível de perguntas

O exemplo a seguir mostra uma IVR que usa um nível de perguntas. Usa reconhecimento de voz para detectar a resposta do chamador.

**Pergunta:** "Obrigado por ligar para os Recursos Humanos. Se você deseja falar com a folha de pagamentos, diga folha de pagamentos. Caso contrário, diga RH."

  - **A opção 1 é selecionada:** O chamador é roteado para a equipe de folha de pagamentos.

  - **A opção 2 é selecionada:** O chamador é roteado para a equipe de recursos humanos.

A figura a seguir mostra o fluxo da chamada.

**Fluxo de chamada interativa de um nível**

![Projetar fluxos de chamada usando o interativa de voz interativo](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "Projetar fluxos de chamada usando o interativa de voz interativo")

</div>

<div>

## <a name="ivr-with-two-levels-of-questions"></a>IVR com dois níveis de perguntas

O exemplo a seguir mostra uma IVR que usa dois níveis de perguntas. Permite aos chamadores responder usando fala ou entrada do teclado DTMF.

**Pergunta:** "Obrigado por ligar para o Help Desk de TI. Se você está com um problema de acesso à rede, pressione 1 ou diga rede. Se você está com um problema de software, pressione 2 ou diga software. Se você está com um problema de hardware, pressione 3 ou diga hardware."

  - **A opção 1 é selecionada:** O chamador é roteado para a equipe de suporte de rede.

  - **A opção 2 é selecionada:** É realizada uma pergunta de acompanhamento ao chamador:
    
    **Pergunta:** "Se é um problema do sistema operacional, pressione 1 ou diga sistema operacional. Se é um problema com um aplicativo interno, pressione 2 ou diga aplicativo interno. Caso contrário, pressione 3 ou diga outro."
    
      - **A opção 1 é selecionada:** O chamador é roteado para a equipe de suporte ao sistema operacional.
    
      - **A opção 2 é selecionada:** O chamador é roteado para a equipe de suporte a aplicativos internos.
    
      - **A opção 3 é selecionada:** O chamador é roteado para a equipe de suporte de software.

  - **A opção 3 é selecionada:** É realizada uma pergunta de acompanhamento ao chamador:
    
    **Pergunta:** "Se é um problema de impressora, pressione 1. Caso contrário, pressione 2."
    
      - **A opção 1 é selecionada:** O chamador é roteado para a equipe de suporte a impressoras.
    
      - **A opção 2 é selecionada:** O chamador é roteado para a equipe de suporte ao hardware.

A figura a seguir mostra o fluxo de chamadas.

**Fluxo de chamada interativa de dois níveis**

![Projetar fluxos de chamada usando o interativa de voz interativo](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "Projetar fluxos de chamada usando o interativa de voz interativo")

</div>

</div>

<div>

## <a name="best-practices"></a>Práticas recomendadas

A lista a seguir descreve algumas práticas recomendadas para projetar sua IVR:

  - Permita que o chamador chegue à tarefa rapidamente. Evite oferecer muita informação ou mensagens de marketing longas em sua IVR.

  - Se você deseja incluir uma mensagem longa, considere anexá-la à primeira pergunta ao invés da mensagem de boas-vindas. Os chamadores podem ignorar a mensagem se fizer parte da primeira pergunta respondendo à pergunta, mas não podem ignorar a mensagem de boas-vindas.

  - Fale no idioma do chamador. Evite usar uma linguagem refinada. Fale naturalmente.

  - Grave prompts eficazes e eficientes. Remova qualquer opção desnecessária. Estruture a informação para que a resposta esperada do chamador esteja no final da frase. Por exemplo, "Para falar com a equipe de vendas, pressione 1."

  - Torne as respostas de voz fáceis. Por exemplo, se você especificar as respostas DTMF e voz, use algo como: "Para falar com a equipe de vendas, pressione 1 ou diga vendas."

  - Teste a IVR em um grupo de usuários antes de implantar na sua organização.

</div>

</div>

<span> </span>

</div>

</div>

</div>

