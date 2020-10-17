---
title: 'Lync Server 2013: projetar fluxos de chamada de resposta interativa de voz'
description: 'Lync Server 2013: projetar fluxos de chamada de resposta interativa de voz.'
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
ms.openlocfilehash: ccf80c1e3226052d952697a4d9fb967f3b681c95
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555307"
---
# <a name="design-interactive-voice-response-call-flows-in-lync-server-2013"></a><span data-ttu-id="7579e-103">Projetar fluxos de chamada de resposta interativa de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7579e-103">Design interactive voice response call flows in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7579e-104">_**Última modificação do tópico:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="7579e-104">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="7579e-p101">É possível usar a resposta de voz interativa (IVR) para obter as informações dos chamadores e enviar a chamada para a fila adequada. Pares de perguntas e respostas determinam a fila a usar. Dependendo da resposta do chamador, o chamador ouve uma pergunta de acompanhamento ou é roteado para a fila adequada. As perguntas IVR e as respostas do chamador são oferecidas para o agente de resposta quando ele ou ela aceitar a chamada. O sistema oferece informações valiosas para o agente de resposta.</span><span class="sxs-lookup"><span data-stu-id="7579e-p101">You can use interactive voice response (IVR) to obtain information from callers and direct the call to the appropriate queue. Question-and-answer pairs determine which queue to use. Depending on the caller’s response, the caller either hears a follow-up question, or is routed to the appropriate queue. The IVR questions and the caller’s responses are provided to the responding agent who accepts the call, providing valuable information to the agent.</span></span>

<div>

## <a name="overview-of-ivr-features"></a><span data-ttu-id="7579e-109">Visão geral dos recursos do IVR</span><span class="sxs-lookup"><span data-stu-id="7579e-109">Overview of IVR Features</span></span>

<span data-ttu-id="7579e-110">O aplicativo grupo de resposta oferece recursos de reconhecimento de fala e conversão de texto em fala em 26 idiomas.</span><span class="sxs-lookup"><span data-stu-id="7579e-110">The Response Group application offers speech recognition and text-to-speech capabilities in 26 languages.</span></span> <span data-ttu-id="7579e-111">É possível inserir perguntas IVR usando a conversão texto em fala ou um arquivo wave (.wav) ou Windows Media audio (.wma).</span><span class="sxs-lookup"><span data-stu-id="7579e-111">You can enter IVR questions using text-to-speech or a wave (.wav) or Windows Media audio (.wma) file.</span></span> <span data-ttu-id="7579e-112">Os chamadores podem responder usando a voz ou multifrequência de dois tons (DTMF).</span><span class="sxs-lookup"><span data-stu-id="7579e-112">Callers can respond by using voice or dual-tone multifrequency (DTMF) responses.</span></span>

<span data-ttu-id="7579e-p103">Os fluxos de trabalho interativos suportam até dois níveis de perguntas, com cada pergunta tendo até quatro respostas possíveis. A IVR faz uma pergunta ao chamador e, dependendo da resposta, roteia o chamador para uma fila ou faz uma segunda pergunta. A segunda pergunta também pode ter quatro respostas possíveis. Dependendo da resposta à pergunta de segundo nível, o chamador é roteado para a fila adequada.</span><span class="sxs-lookup"><span data-stu-id="7579e-p103">Interactive workflows support up to two levels of questions, with each question having up to four possible answers. The IVR asks the caller a question, and depending on the caller’s response, routes the caller to a queue or asks a second question. The second question can also have four possible answers. Depending on the answer to the second-level question, the caller is routed to the appropriate queue.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7579e-117">Ao projetar fluxos de chamadas usando o Shell de gerenciamento do Lync Server, você pode definir qualquer nível de número de perguntas IVR e qualquer número de respostas.</span><span class="sxs-lookup"><span data-stu-id="7579e-117">When you design call flows by using Lync Server Management Shell, you can define any number levels of IVR questions and any number of answers.</span></span> <span data-ttu-id="7579e-118">No entanto, para melhor usabilidade do chamador, recomendamos que você não use mais de três níveis de perguntas, com não mais do que cinco respostas cada.</span><span class="sxs-lookup"><span data-stu-id="7579e-118">However, for caller usability, we recommend that you not use more than three levels of questions, with not more than five answers each.</span></span> <span data-ttu-id="7579e-119">Além disso, se você criar um fluxo de chamadas com mais de dois níveis de perguntas com mais de quatro respostas, não será possível editar o fluxo de chamadas usando o painel de controle do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7579e-119">In addition, if you design a call flow that has more than two levels of questions with more than four answers each, you cannot edit the call flow by using Lync Server 2013 Control Panel.</span></span>



</div>

<span data-ttu-id="7579e-120">As perguntas IVR e as respostas do chamador são fornecidas para o agente de resposta quando ele ou ela aceita a chamada.</span><span class="sxs-lookup"><span data-stu-id="7579e-120">The IVR questions and the caller’s responses are provided to the responding agent who accepts the call.</span></span>

</div>

<div>

## <a name="working-with-speech-technologies"></a><span data-ttu-id="7579e-121">Trabalhando com tecnologias de fala</span><span class="sxs-lookup"><span data-stu-id="7579e-121">Working with Speech Technologies</span></span>

<span data-ttu-id="7579e-122">Tecnologias de fala, como o reconhecimento de fala e conversão de texto em fala, podem aprimorar a experiência do cliente e permitir que as pessoas acessem informações de forma mais natural e eficaz.</span><span class="sxs-lookup"><span data-stu-id="7579e-122">Speech technologies, such as speech recognition and text-to-speech, can enhance customer experience and let people access information more naturally and effectively.</span></span> <span data-ttu-id="7579e-123">No entanto, pode haver casos em que o texto especificado ou a resposta de voz do usuário não é reconhecido corretamente pelo mecanismo de fala.</span><span class="sxs-lookup"><span data-stu-id="7579e-123">However, there can be cases where the specified text or the user voice response is not recognized correctly by the speech engine.</span></span> <span data-ttu-id="7579e-124">Por exemplo, o \# símbolo "" é traduzido pelo mecanismo de conversão de texto em fala como a palavra "número".</span><span class="sxs-lookup"><span data-stu-id="7579e-124">For example, the "\#" symbol is translated by the text-to-speech engine as the word "number."</span></span> <span data-ttu-id="7579e-125">Este problema pode ser reduzido pelo seguinte:</span><span class="sxs-lookup"><span data-stu-id="7579e-125">This issue can be mitigated by the following:</span></span>

  - <span data-ttu-id="7579e-p106">O mecanismo de fala fornece ao chamador cinco tentativas de responder a pergunta. Se o chamador responder incorretamente (isto é, a resposta não é uma das respostas especificadas) ou não oferecer uma resposta, ele ou ela tem outra chance de responder. O chamador tem cinco tentativas de responder a pergunta antes de ser desconectado. É possível configurar a IVR para reproduzir uma mensagem personalizada após cada erro do chamador. A pergunta é repetida todas as vezes.</span><span class="sxs-lookup"><span data-stu-id="7579e-p106">The speech engine gives the caller five attempts to answer the question. If the caller answers the question incorrectly (that is, the answer is not one of the specified responses) or does not provide an answer at all, the caller gets another chance to answer the question. The caller has five attempts to answer the question before being disconnected. You can configure the IVR to play a customized message after each caller error. The question is repeated each time.</span></span>

  - <span data-ttu-id="7579e-p107">Para minimizar que o potencial ruído ambiente seja interpretado pelo mecanismo de fala como uma resposta, use respostas mais longas. Por exemplo, as respostas devem ter mais de uma sílaba e devem soar diferente uma da outra.</span><span class="sxs-lookup"><span data-stu-id="7579e-p107">To minimize the potential for ambient noise to be interpreted by the speech engine as a response, use longer responses. For example, responses should have more than one syllable and should sound significantly different from each other.</span></span>

  - <span data-ttu-id="7579e-p108">Se suas perguntas possuem respostas de fala e DTMF, configure as respostas de fala com palavras que representam um conceito ao invés da resposta DTMF. Por exemplo, ao invés de usar "Pressione ou fale 1", use "Pressione 1 ou fale faturamento."</span><span class="sxs-lookup"><span data-stu-id="7579e-p108">If your questions have both speech and DTMF responses, configure the speech responses with words that represent the concept rather than the DTMF response. For example, instead of using "Press or say one" use "Press 1 or say billing."</span></span>

  - <span data-ttu-id="7579e-135">Após projetar sua IVR, ligue par ao fluxo de trabalho, ouça às solicitações, responda cada uma delas usando a voz e verifique se a IVR soa e se comporta conforme esperado.</span><span class="sxs-lookup"><span data-stu-id="7579e-135">After you design your IVR, call the workflow, listen to the prompts, respond to each of the prompts using voice, and verify that the IVR sounds and behaves as expected.</span></span> <span data-ttu-id="7579e-136">É possível modificar a IVR para corrigir qualquer problema de interpretação.</span><span class="sxs-lookup"><span data-stu-id="7579e-136">You can then modify the IVR to fix any interpretation issues.</span></span> <span data-ttu-id="7579e-137">Após o exemplo anterior, se você precisar fazer referência à \# chave, você pode reconfigurar seu prompt IVR para usar o nome da chave, em vez do \# símbolo.</span><span class="sxs-lookup"><span data-stu-id="7579e-137">Following the previous example, if you need to refer to the \# key, you can rewrite your IVR prompt to use the key name, rather than the \# symbol.</span></span> <span data-ttu-id="7579e-138">Por exemplo, "Para falar com vendas, pressione a tecla jogo da velha."</span><span class="sxs-lookup"><span data-stu-id="7579e-138">For example, "To talk to sales, press the pound key."</span></span>

</div>

<div>

## <a name="ivr-design-examples"></a><span data-ttu-id="7579e-139">Exemplos de design de IVR</span><span class="sxs-lookup"><span data-stu-id="7579e-139">IVR Design Examples</span></span>

<span data-ttu-id="7579e-140">As seções a seguir contêm exemplos de diferentes cenários de IVR e pares de perguntas e respostas.</span><span class="sxs-lookup"><span data-stu-id="7579e-140">The following sections contain examples of different IVR scenarios and question-and-answer pairs.</span></span>

<div>

## <a name="ivr-with-one-level-of-questions"></a><span data-ttu-id="7579e-141">IVR com um nível de perguntas</span><span class="sxs-lookup"><span data-stu-id="7579e-141">IVR with One Level of Questions</span></span>

<span data-ttu-id="7579e-p110">O exemplo a seguir mostra uma IVR que usa um nível de perguntas. Usa reconhecimento de voz para detectar a resposta do chamador.</span><span class="sxs-lookup"><span data-stu-id="7579e-p110">The following example shows an IVR that uses one level of questions. It uses speech recognition to detect the caller’s response.</span></span>

<span data-ttu-id="7579e-p111">**Pergunta:** "Obrigado por ligar para os Recursos Humanos. Se você deseja falar com a folha de pagamentos, diga folha de pagamentos. Caso contrário, diga RH."</span><span class="sxs-lookup"><span data-stu-id="7579e-p111">**Question:** "Thank you for calling Human Resources. If you would like to speak to payroll, say payroll. Otherwise, say HR."</span></span>

  - <span data-ttu-id="7579e-147">**A opção 1 é selecionada:** O chamador é roteado para a equipe de folha de pagamentos.</span><span class="sxs-lookup"><span data-stu-id="7579e-147">**Option 1 is selected:** The caller is routed to the payroll team.</span></span>

  - <span data-ttu-id="7579e-148">**A opção 2 é selecionada:** O chamador é roteado para a equipe de recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="7579e-148">**Option 2 is selected:** The caller is routed to the human resources team.</span></span>

<span data-ttu-id="7579e-149">A figura a seguir mostra o fluxo da chamada.</span><span class="sxs-lookup"><span data-stu-id="7579e-149">The following figure shows the call flow.</span></span>

<span data-ttu-id="7579e-150">**Fluxo de chamada interativa de um nível**</span><span class="sxs-lookup"><span data-stu-id="7579e-150">**One-level interactive call flow**</span></span>

<span data-ttu-id="7579e-151">![Projetar fluxos de chamada usando o interativa de voz interativo](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "Projetar fluxos de chamada usando o interativa de voz interativo")</span><span class="sxs-lookup"><span data-stu-id="7579e-151">![Design Call Flows by Using Interactive Voice Respo](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "Design Call Flows by Using Interactive Voice Respo")</span></span>

</div>

<div>

## <a name="ivr-with-two-levels-of-questions"></a><span data-ttu-id="7579e-152">IVR com dois níveis de perguntas</span><span class="sxs-lookup"><span data-stu-id="7579e-152">IVR with Two Levels of Questions</span></span>

<span data-ttu-id="7579e-p112">O exemplo a seguir mostra uma IVR que usa dois níveis de perguntas. Permite aos chamadores responder usando fala ou entrada do teclado DTMF.</span><span class="sxs-lookup"><span data-stu-id="7579e-p112">The following example shows an IVR that uses two levels of questions. It allows callers to respond using either speech or DTMF keypad input.</span></span>

<span data-ttu-id="7579e-p113">**Pergunta:** "Obrigado por ligar para o Help Desk de TI. Se você está com um problema de acesso à rede, pressione 1 ou diga rede. Se você está com um problema de software, pressione 2 ou diga software. Se você está com um problema de hardware, pressione 3 ou diga hardware."</span><span class="sxs-lookup"><span data-stu-id="7579e-p113">**Question:** "Thank you for calling the IT Help Desk. If you have a network access problem, press 1 or say network. If you have a software problem, press 2 or say software. If you have a hardware problem, press 3 or say hardware."</span></span>

  - <span data-ttu-id="7579e-159">**A opção 1 é selecionada:** O chamador é roteado para a equipe de suporte de rede.</span><span class="sxs-lookup"><span data-stu-id="7579e-159">**Option 1 is selected:** The caller is routed to the network support team.</span></span>

  - <span data-ttu-id="7579e-160">**A opção 2 é selecionada:** É realizada uma pergunta de acompanhamento ao chamador:</span><span class="sxs-lookup"><span data-stu-id="7579e-160">**Option 2 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="7579e-p114">**Pergunta:** "Se é um problema do sistema operacional, pressione 1 ou diga sistema operacional. Se é um problema com um aplicativo interno, pressione 2 ou diga aplicativo interno. Caso contrário, pressione 3 ou diga outro."</span><span class="sxs-lookup"><span data-stu-id="7579e-p114">**Question:** "If this is an operating system problem, press 1 or say operating system. If this is a problem with an internal application, press 2 or say internal application. Otherwise, press 3 or say other."</span></span>
    
      - <span data-ttu-id="7579e-164">**A opção 1 é selecionada:** O chamador é roteado para a equipe de suporte ao sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="7579e-164">**Option 1 is selected:** The caller is routed to the operating systems support team.</span></span>
    
      - <span data-ttu-id="7579e-165">**A opção 2 é selecionada:** O chamador é roteado para a equipe de suporte a aplicativos internos.</span><span class="sxs-lookup"><span data-stu-id="7579e-165">**Option 2 is selected:** The caller is routed to the internal applications support team.</span></span>
    
      - <span data-ttu-id="7579e-166">**A opção 3 é selecionada:** O chamador é roteado para a equipe de suporte de software.</span><span class="sxs-lookup"><span data-stu-id="7579e-166">**Option 3 is selected:** The caller is routed to the software support team.</span></span>

  - <span data-ttu-id="7579e-167">**A opção 3 é selecionada:** É realizada uma pergunta de acompanhamento ao chamador:</span><span class="sxs-lookup"><span data-stu-id="7579e-167">**Option 3 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="7579e-p115">**Pergunta:** "Se é um problema de impressora, pressione 1. Caso contrário, pressione 2."</span><span class="sxs-lookup"><span data-stu-id="7579e-p115">**Question:** "If this is a printer problem press 1. Otherwise, press 2."</span></span>
    
      - <span data-ttu-id="7579e-170">**A opção 1 é selecionada:** O chamador é roteado para a equipe de suporte a impressoras.</span><span class="sxs-lookup"><span data-stu-id="7579e-170">**Option 1 is selected:** The caller is routed to the printer support team.</span></span>
    
      - <span data-ttu-id="7579e-171">**A opção 2 é selecionada:** O chamador é roteado para a equipe de suporte ao hardware.</span><span class="sxs-lookup"><span data-stu-id="7579e-171">**Option 2 is selected:** The caller is routed to the hardware support team.</span></span>

<span data-ttu-id="7579e-172">A figura a seguir mostra o fluxo de chamadas.</span><span class="sxs-lookup"><span data-stu-id="7579e-172">The following figure shows the call flow.</span></span>

<span data-ttu-id="7579e-173">**Fluxo de chamada interativa de dois níveis**</span><span class="sxs-lookup"><span data-stu-id="7579e-173">**Two-level interactive call flow**</span></span>

<span data-ttu-id="7579e-174">![Projetar fluxos de chamada usando o interativa de voz interativo](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "Projetar fluxos de chamada usando o interativa de voz interativo")</span><span class="sxs-lookup"><span data-stu-id="7579e-174">![Design Call Flows by Using Interactive Voice Respo](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "Design Call Flows by Using Interactive Voice Respo")</span></span>

</div>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="7579e-175">Práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="7579e-175">Best Practices</span></span>

<span data-ttu-id="7579e-176">A lista a seguir descreve algumas práticas recomendadas para projetar sua IVR:</span><span class="sxs-lookup"><span data-stu-id="7579e-176">The following list describes some best practices for designing your IVR:</span></span>

  - <span data-ttu-id="7579e-p116">Permita que o chamador chegue à tarefa rapidamente. Evite oferecer muita informação ou mensagens de marketing longas em sua IVR.</span><span class="sxs-lookup"><span data-stu-id="7579e-p116">Let the caller get to the task quickly. Avoid providing too much information or lengthy marketing messages in your IVR.</span></span>

  - <span data-ttu-id="7579e-p117">Se você deseja incluir uma mensagem longa, considere anexá-la à primeira pergunta ao invés da mensagem de boas-vindas. Os chamadores podem ignorar a mensagem se fizer parte da primeira pergunta respondendo à pergunta, mas não podem ignorar a mensagem de boas-vindas.</span><span class="sxs-lookup"><span data-stu-id="7579e-p117">If you want to include a lengthy message, consider appending it to the first question instead of to the welcome message. Callers can bypass the message if it is part of the first question by answering the question, but they cannot bypass the welcome message.</span></span>

  - <span data-ttu-id="7579e-p118">Fale no idioma do chamador. Evite usar uma linguagem refinada. Fale naturalmente.</span><span class="sxs-lookup"><span data-stu-id="7579e-p118">Speak in the caller’s language. Avoid stilted language. Speak naturally.</span></span>

  - <span data-ttu-id="7579e-p119">Grave prompts eficazes e eficientes. Remova qualquer opção desnecessária. Estruture a informação para que a resposta esperada do chamador esteja no final da frase. Por exemplo, "Para falar com a equipe de vendas, pressione 1."</span><span class="sxs-lookup"><span data-stu-id="7579e-p119">Write efficient and effective prompts. Remove any unnecessary options. Structure the information so that the caller’s expected response is at the end of the sentence. For example, “To speak to the sales team, press 1."</span></span>

  - <span data-ttu-id="7579e-p120">Torne as respostas de voz fáceis. Por exemplo, se você especificar as respostas DTMF e voz, use algo como: "Para falar com a equipe de vendas, pressione 1 ou diga vendas."</span><span class="sxs-lookup"><span data-stu-id="7579e-p120">Make voice responses user friendly. For example, if you specify both DTMF and voice responses, use something like: "To speak to the sales team, press 1 or say sales."</span></span>

  - <span data-ttu-id="7579e-190">Teste a IVR em um grupo de usuários antes de implantar na sua organização.</span><span class="sxs-lookup"><span data-stu-id="7579e-190">Test the IVR on a group of users before you deploy it across your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

