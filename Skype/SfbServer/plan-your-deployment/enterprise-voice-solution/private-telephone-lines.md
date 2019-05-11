---
title: Plano para linhas telefônicas privadas com Skype para negócios
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: Planejando para linhas telefônicas privadas de (secundário) Skype Business Server Enterprise Voice.
ms.openlocfilehash: 527ebc75311fdab280d258c0fd7f331f78056717
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913597"
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business"></a>Plano para linhas telefônicas privadas com Skype para negócios
 
Planejando para linhas telefônicas privadas de (secundário) Skype Business Server Enterprise Voice.
  
Skype para Business Server permite fornecer aos usuários uma linha telefônica privada, de segunda além dos seu linha telefônica principal. Linhas telefônicas privadas são frequentemente atribuídas a executivos e a outras pessoas que desejam um número de telefone não listado e através do qual podem ser diretamente contatados.
  
Linhas telefônicas privadas só podem ser configuradas com o Skype do Shell de gerenciamento do servidor de negócios. Você não pode configurar linhas telefônicas privadas com o Skype para painel de controle do servidor de negócios. Linhas telefônicas privadas devem ser configuradas somente em implantações do Skype para Business Server e não em implantações mistas.
  
## <a name="characteristics-of-private-telephone-lines"></a>Características das linhas telefônicas privadas

Embora o conceito de uma linha telefônica privada, de segunda fundamentalmente simple, é importante compreender as características das linhas privadas e das formas nas quais elas são semelhantes às e diferentes das linhas de telefone principal dos usuários.
  
### <a name="general-characteristics-of-private-telephone-lines"></a>Características gerais das linhas telefônicas privadas

- Um usuário pode ter somente uma linha telefônica privada.
    
- Um usuário com uma linha telefônica privada só possui uma caixa postal e recebe notificações de chamadas perdidas em um único endereço de e-mail.
    
- Um usuário com uma linha telefônica privada não possui um segundo endereço SIP e uma linha telefônica privada secundária não dá a ele uma segunda presença na rede (como uma segunda identidade no sistema de mensagens instantâneas). 
    
- Linhas telefônicas privadas estão disponíveis somente para implantações locais. Eles não estão disponíveis com implantações hospedadas do Skype para Business Server.
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>Como linhas telefônicas privadas diferem de linhas telefônicas principais

- Os números de telefone para linhas telefônicas privadas não aparecem nos diretórios telefônicos ou listas de Contatos derivados dos Serviços de Domínio do Active Directory.
    
- Nenhum dos recursos a seguir está disponível com uma linha telefônica privada: encaminhamento de chamadas, chamada de equipe, delegação, toque de equipe, recebimento de chamadas de grupo e aplicativo Grupo de Resposta.
    
- Chamadas para uma linha telefônica privada têm um toque especial e a notificação do sistema para as chamadas diz ao usuário que a chamada de entrada está em sua linha privada.
    
- Chamadas para a linha telefônica privada sempre tocam. Elas não seguem as regras "não incomodar".
    
- Linhas telefônicas privadas são somente de entrada e não podem ser usadas para fazer chamadas de saída. Quando um usuário com uma linha telefônica privada faz uma chamada, a chamada for originada da linha de telefone principal do usuário e não oculta o nome do usuário ou número de telefone principal do usuário da pessoa chamada.
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>Como linhas telefônicas privadas são similares a linhas telefônicas principais

- Chamadas não atendidas para uma linha telefônica privada são roteadas para a mesma caixa postal da linha telefônica principal (se a caixa postal estiver habilitada).
    
- Estacionamento de chamada e o recebimento de chamadas funcionam com linhas telefônicas privadas exatamente da mesma maneira que funcionam com a linha telefônica principal do usuário.
    
- Quando o toque simultâneo está habilitado na linha telefônica principal de um usuário, ele também é habilitado na linha telefônica privada.
    
- O número de telefone para uma linha telefônica privada é registrado no registro de detalhe de chamada da mesma maneira como o número de telefone para a linha telefônica principal de um usuário, mas com uma indicação de que é um número de telefone privada.
    
- Depois que um usuário respostas que uma chamada em uma linha telefônica privada, a chamada é tratada como uma chamada em uma linha telefônica principal do usuário. Por exemplo, se um usuário que recebe uma chamada em uma linha telefônica privada encaminha a chamada ou convida outras pessoas a uma chamada em conferência, o nome do usuário aparece no Skype para a empresa e o número de telefone para a linha de telefone principal do usuário aparece no chamador ID.
    
- Um usuário pode desviar uma chamada (redirecionar para outro destino, como um telefone celular ou residencial, antes de atender) a partir da linha telefônica privada da mesma maneira como o faria com uma linha telefônica principal. 
    
    > [!NOTE]
    > Quando uma chamada para uma linha privada é roteada para um número de telefone alternativo, o número para a linha telefônica privada é disponibilizado para o número de telefone alternativo e pode ser exibido nos logs para aquele número. 
  
    > [!NOTE]
    > Chamadas de uma conferência para a linha telefônica privada não terão uma indicação de *linha privada* na notificação de sistema de entrada.
  
## <a name="administering-private-telephone-lines"></a>Como administrar linhas telefônicas privadas

Além dos aspectos técnicos da criação e gerenciamento de linhas telefônicas privadas, você precisará estabelecer procedimentos administrativos para elas. Isso inclui determinar políticas para quem na organização está elegível para uma linha privada, criar e manter listas de pessoas e suas linhas telefônicas, possivelmente criar um diretório de telefonia privada para executivos, providenciar o treinamento dos usuários e tarefas relacionadas.
  
> [!NOTE]
> A linha telefônica privada é armazenada no Active Directory como um atributo msRTCSIP-PrivateLine no objeto do usuário. Por padrão, qualquer membro do grupo Usuários Autenticados tem acesso de leitura a este atributo. 
  
### <a name="assigning-telephone-numbers"></a>Como atribuir números de telefone

 Contas para novos usuários que precisam de linhas telefônicas privadas são criadas da mesma maneira como as contas sem linhas telefônicas privadas, usando Skype para painel de controle de servidor de negócios ou Skype para Business Server Management Shell.
  
Use o cmdlet **Set-CsUser** no Skype para Business Server Management Shell para atribuir um número de telefone a uma linha telefônica privada para um usuário, por exemplo, **Set-CsUser-Identity "sip:joe@contoso.com" - PrivateLine "Tel: + 14255551212"**.
  
Números de telefone para linhas telefônicas privadas pode estar entre 3 e 15 números de comprimento e deve ser precedidos com o "TEL:" prefixo. Podem ter qualquer código de área e qualquer código de país/região, desde que sua organização tenha discagem interna direta para aquele código de área e código de país/região. 
  
Para obter detalhes sobre cmdlets e Skype do Shell de gerenciamento do servidor de negócios, consulte o Skype para obter a documentação do Shell de gerenciamento do servidor de negócios.
  
### <a name="private-telephone-lines-in-mixed-deployments"></a>Linhas telefônicas privadas em implantações mistas

Linhas telefônicas privadas devem ser configuradas somente para implantações do Skype para Business Server ou o Lync Server 2013. Em uma implantação no qual há servidores que executam versões anteriores do Lync Server, quando um usuário da versão anterior tenta chamar uma linha telefônica privada, roteamento da chamada falha porque o servidor não pode executar uma pesquisa inversa de números em uma linha telefônica privada.
  

