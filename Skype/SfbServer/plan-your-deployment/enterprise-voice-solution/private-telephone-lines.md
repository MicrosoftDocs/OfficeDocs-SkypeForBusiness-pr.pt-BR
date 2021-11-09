---
title: Planejar linhas telefônicas privadas com Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: Planejamento de linhas telefônicas privadas (secundárias) Skype for Business Server Enterprise Voice.
ms.openlocfilehash: a9054266cc5092f77e0fecd66b71b7180c89018c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861078"
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business"></a>Planejar linhas telefônicas privadas com Skype for Business
 
Planejamento de linhas telefônicas privadas (secundárias) Skype for Business Server Enterprise Voice.
  
Skype for Business Server permite que você dê aos usuários uma segunda linha telefônica privada, além da linha telefônica principal. Linhas telefônicas privadas são frequentemente atribuídas a executivos e a outras pessoas que desejam um número de telefone não esteja listado e através do qual podem ser diretamente contatados.
  
Linhas telefônicas privadas só podem ser configuradas com o Shell Skype for Business Server Gerenciamento. Não é possível configurar linhas telefônicas privadas com o Skype for Business Server Painel de Controle. Linhas telefônicas privadas devem ser configuradas somente em implantações de Skype for Business Server e não em implantações mistas.
  
## <a name="characteristics-of-private-telephone-lines"></a>Características das linhas telefônicas privadas

Embora o conceito de uma segunda linha telefônica privada seja fundamentalmente simples, é importante compreender as características das linhas privadas e as maneiras pelas quais elas são semelhantes e diferentes das linhas telefônicas principais dos usuários.
  
### <a name="general-characteristics-of-private-telephone-lines"></a>Características gerais das linhas telefônicas privadas

- Um usuário pode ter somente uma linha telefônica privada.
    
- Um usuário com uma linha telefônica privada só possui uma caixa postal e recebe notificações de chamadas perdidas em um único endereço de e-mail.
    
- Um usuário com uma linha telefônica privada não possui um segundo endereço SIP e uma linha telefônica privada secundária não dá a ele uma segunda presença na rede (como uma segunda identidade no sistema de mensagens instantâneas). 
    
- Linhas telefônicas privadas estão disponíveis somente para implantações locais. Eles não estão disponíveis com implantações hospedadas de Skype for Business Server.
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>Como linhas telefônicas privadas diferem de linhas telefônicas principais

- Os números de telefone para linhas telefônicas privadas não aparecem nos diretórios telefônicos ou listas de Contatos derivados dos Serviços de Domínio do Active Directory.
    
- Nenhum dos seguintes recursos está disponível com uma linha telefônica privada: encaminhamento de chamadas, chamada de equipe, delegação, anel de equipe, Retirada de Chamadas de Grupo e aplicativo grupo de resposta.
    
- Chamadas para uma linha telefônica privada possuem um toque especial e a notificação do sistema para as chamadas diz ao usuário que a chamada de entrada está em sua linha privada.
    
- Chamadas para a linha telefônica privada sempre tocam. Elas não seguem as regras "não incomodar".
    
- Linhas telefônicas privadas são somente de entrada e não podem ser usadas para fazer chamadas de saída. Quando um usuário com uma linha telefônica privada faz uma chamada, a chamada se origina da linha telefônica principal do usuário e não oculta o nome do usuário ou o número de telefone principal do usuário da pessoa chamada.
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>Como linhas telefônicas privadas são similares a linhas telefônicas principais

- Chamadas não atendidas para uma linha telefônica privada são roteadas para a mesma caixa postal da linha telefônica principal (se a caixa postal estiver habilitada).
    
- Estacionamento de chamadas e retirada de chamadas funcionam com linhas telefônicas privadas exatamente da mesma maneira que fazem com a linha telefônica principal do usuário.
    
- Quando o toque simultâneo é habilitado na linha telefônica principal do usuário, ele também é habilitado na linha telefônica privada.
    
- O número de telefone de uma linha telefônica privada é gravado no registro de detalhes da chamada da mesma maneira que o número de telefone da linha telefônica principal de um usuário, mas com uma indicação de que é um número de telefone privado.
    
- Depois que um usuário atende uma chamada em uma linha telefônica privada, a chamada é tratada da mesma forma que uma chamada na linha telefônica principal do usuário. Por exemplo, se um usuário que recebe uma chamada em uma linha telefônica privada encaminhar a chamada ou convidar outras pessoas para uma chamada de conferência, o nome do usuário aparecerá no Skype for Business e o número de telefone da linha telefônica principal do usuário aparecerá na ID do chamador.
    
- Um usuário pode desviar uma chamada (redirecionar para outro destino, como um telefone celular ou residencial, antes de atender) a partir da linha telefônica privada da mesma maneira como o faria com uma linha telefônica principal. 
    
    > [!NOTE]
    > Quando uma chamada para uma linha privada é roteada para um número de telefone alternativo, o número para a linha telefônica privada é disponibilizado para o número de telefone alternativo e pode ser exibido nos logs para aquele número. 
  
    > [!NOTE]
    > As chamadas de uma conferência para a linha telefônica privada não terão  *uma*  indicação de linha privada na notificação do sistema de entrada.
  
## <a name="administering-private-telephone-lines"></a>Como administrar linhas telefônicas privadas

Além dos aspectos técnicos da criação e gerenciamento de linhas telefônicas privadas, você precisará estabelecer procedimentos administrativos para elas. Isso inclui determinar políticas para quem na organização está elegível para uma linha privada, criar e manter listas de pessoas e suas linhas telefônicas, possivelmente criar um diretório de telefonia privada para executivos, providenciar o treinamento dos usuários e tarefas relacionadas.
  
> [!NOTE]
> A linha telefônica privada é armazenada no Active Directory como um atributo msRTCSIP-PrivateLine no objeto do usuário. Por padrão, qualquer membro do grupo Usuários Autenticados tem acesso de leitura a este atributo. 
  
### <a name="assigning-telephone-numbers"></a>Como atribuir números de telefone

 Contas para novos usuários que precisam de linhas telefônicas privadas são criadas da mesma maneira que contas sem linhas telefônicas privadas, usando o Painel de Controle Skype for Business Server ou o Shell de Gerenciamento Skype for Business Server.
  
Use o cmdlet **Set-CsUser** no Shell de Gerenciamento do Skype for Business Server para atribuir um número de telefone a uma linha telefônica privada para um usuário, por exemplo, **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**.
  
Os números de telefone para linhas telefônicas privadas podem ter entre 3 e 15 números de comprimento e devem ser precedidas com o prefixo "TEL:". Podem ter qualquer código de área e qualquer código de país/região, desde que sua organização tenha discagem interna direta para aquele código de área e código de país/região. 
  
Para obter detalhes sobre cmdlets e Skype for Business Server Shell de Gerenciamento, consulte a documentação Skype for Business Server Shell de Gerenciamento.
  
### <a name="private-telephone-lines-in-mixed-deployments"></a>Linhas telefônicas privadas em implantações mistas

As linhas telefônicas privadas devem ser configuradas apenas para implantações de Skype for Business Server ou Lync Server 2013. Em uma implantação na qual há servidores executando versões anteriores do Lync Server, quando um usuário na versão anterior tenta chamar uma linha telefônica privada, o roteamento da chamada falha porque o servidor não pode executar uma busca de número reverso em uma linha telefônica privada.
  

