---
title: Instalar e testar o Skype for Business para Windows Phone
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 54289bbe-97e7-44bf-8611-4e740fc5b998
description: 'Resumo: Saiba como instalar e testar Skype for Business no seu Windows Phone.'
ms.openlocfilehash: 0e135441a711655e42c37d0a9bd7ff4870da1d0d
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372927"
---
# <a name="install-and-test-skype-for-business-for-windows-phone"></a>Skype for Business Server 2015: Instalar e testar o Skype for Business para Windows Phone
 
**Resumo:** Saiba como instalar e testar Skype for Business no seu Windows Phone.
  
O Skype para o aplicativo de negócios para o Windows Phone traz Skype para presença, mensagens instantâneas (IM) e voz e vídeo chamar para dispositivos móveis do Windows de negócios. Usuários com Lync 2013 receberão o aplicativo atualizado automaticamente ou serão solicitados a atualizá-lo manualmente, dependendo das configurações do usuário. Novos usuários podem baixá-lo no [Windows Phone Marketplace](https://go.microsoft.com/fwlink/p/?linkid=231901). O Skype para o aplicativo de negócios para o Windows Phone só está disponível no Windows Phone 8.1 e posterior.
  
Antes que orienta os usuários em sua organização para baixar o aplicativo, convém executar os seguintes testes para certificar-se de que ele adequadamente é integrado ao seu ambiente. 
  
## <a name="install-skype-for-business-windows-phone-81"></a>Instale o Skype para Windows Phone de negócios 8.1

1. Navegue para o [Windows Phone 8 atualizar central](https://www.windowsphone.com/en-us/how-to/wp8/update-central) para atualizar o seu telefone para Windows Phone 8.1.
    
2. Em seu telefone, vá para o **repositório**e procurar **Skype para negócios**.
    
3. Toque em **Instalar**. 
    
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Entrar no Skype for Business pela primeira vez

1. Na tela de **início** , passe o dedo da esquerda para exibir seus aplicativos instalados, procure Skype para Business para Windows Phone e, em seguida, toque no ícone para abrir o aplicativo.
    
2. Insira seu endereço de entrada (por exemplo, user@domain.com) e a senha e toque em **concluído**.
    
     É provável que você precise informar um nome de usuário e um endereço de entrada. O nome de usuário é o que você usa para entrar rede da sua organização, user@domain.com ou domínio \ nomedeusuário.
    
3. Na tela **Programa de Aperfeiçoamento da Experiência do Usuário**, toque em **Ingressar** para enviar dados anônimos sobre problemas e utilização do aplicativo à Microsoft, ou **Não, obrigado** se preferir não participar.
    
4. Na tela **Nunca Perder Chamadas de Trabalho**, insira o número do seu celular com os códigos de país e região. Quando Skype para Business para Windows Phone não é possível usar uma rede de dados via celular ou de Wi-Fi para fazer uma chamada de áudio ou vídeo, você vai ser automaticamente chamado nesse número e conectados à parte de áudio da chamada.
    
5. Toque em **Avançar** e revise as configurações de acesso do catálogo telefônico e a notificação:
    
   - **Notificações de push** Obtenha um alerta quando você recebe uma nova IM ou chamada. Normalmente **Ligado** (recomendado).
    
     > [!IMPORTANT]
     > Se você desativar essa configuração, você não será notificado de mensagens instantâneas, chamadas ou outro Skype para alertas de negócios para o Windows Phone, a menos que o aplicativo está ativo. 
  
   - **Permitir acesso ao catálogo telefônico** Procurar contatos no telefone celular, quando você procurar contatos no Skype Business para Windows Phone.
    
6. Toque em **Avançar** para começar a usar o Skype para Business para Windows Phone.
    
    [Precisa de ajuda entrando?](https://support.office.com/article/6b827683-ad55-471a-bd4b-3d4ec098bf75)
    
## <a name="verify-mobile-client-installation"></a>Verificar instalação do cliente móvel

Depois de configurar o cliente e entrar com êxito, use os seguintes testes para verificar se a sua instalação do Skype para Business para Windows Phone está funcionando corretamente no seu dispositivo móvel.
  
### <a name="search-for-a-contact-in-the-corporate-directory"></a>Procure um contato no diretório corporativo

1. Na lista de Contatos, toque em **Pesquisar**.
    
2. Procure um contato que conste apenas na lista de endereços global.
    
3. Verifique se o nome do contato aparece nos resultados da pesquisa.
    
### <a name="test-instant-messaging-and-presence"></a>Teste mensagens instantâneas e presença

1. Na lista Contatos, toque em um contato.
    
2. No cartão de visita, toque de mensagens instantâneas (IM) ![Ícone de mensagens instantâneas no Skype for Business](../../media/90f8d5fa-7968-4ef7-bf5b-dddf9b893905.png)ícone.
    
3. Verifique se uma janela de mensagens instantâneas (IM) aparece e se é possível digitar e enviar uma IM.
    
### <a name="test-dial-out-conferencing"></a>Teste a conferência discada

1. No Outlook, agende uma Skype para reunião de negócios.
    
2. No seu Windows Phone, abra o convite de reunião.
    
3. Clique no link da reunião para ingressar.
    
4. Atenda à chamada do serviço de conferência e verifique se você está conectado ao áudio da reunião.
    
### <a name="test-push-notifications"></a>Teste as notificações por push

1. Selecione duas contas de usuário diferentes para este teste. 
    
2. Em do usuário do Windows Phone, entrar no Skype para Business para Windows Phone com a conta do usuário.
    
3. Abra outro aplicativo no dispositivo.
    
4. Em um cliente diferente, como o cliente de desktop, faça logon no Skype for Business com a conta do usuário B.
    
5. Envie uma mensagem instantânea do usuário B para o usuário A.
    
6. Verifique se a notificação de IM aparece no dispositivo móvel do usuário.
    
## <a name="remove-skype-for-business-from-your-windows-phone"></a>Remover Skype para negócios de seu Windows Phone

Para remover o Skype para o aplicativo de negócios para o Windows Phone do dispositivo móvel: 
  
1. Na tela de início, passe o dedo para ver a lista de aplicativos. 
    
2. Toque e mantenha o Skype para o aplicativo de negócios para o Windows Phone e selecione **desinstalar**.
    


