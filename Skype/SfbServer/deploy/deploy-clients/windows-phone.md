---
title: Instalar e testar o Skype for Business para Windows Phone
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 54289bbe-97e7-44bf-8611-4e740fc5b998
description: 'Resumo: saiba como instalar e testar o Skype for Business no Windows Phone.'
ms.openlocfilehash: 63d766a566f131bc58540a13e2a19aa2add0700b
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768584"
---
# <a name="install-and-test-skype-for-business-for-windows-phone"></a>Skype for Business Server 2015: Instalar e testar o Skype for Business para Windows Phone
 
**Resumo:** Saiba como instalar e testar o Skype for Business no Windows Phone.
  
O aplicativo Skype for Business para Windows Phone traz a presença do Skype for Business, mensagens instantâneas (IM) e chamadas de voz e vídeo para dispositivos móveis do Windows. Usuários com Lync 2013 receberão o aplicativo atualizado automaticamente ou serão solicitados a atualizá-lo manualmente, dependendo das configurações do usuário. Novos usuários podem baixá-lo do [Windows Phone Marketplace](https://go.microsoft.com/fwlink/p/?linkid=231901). O aplicativo Skype for Business para Windows Phone só está disponível no Windows Phone 8,1 e versões posteriores.
  
Antes de direcionar os usuários em sua organização para baixar o aplicativo, você desejará executar os seguintes testes para garantir que ele esteja devidamente integrado ao seu ambiente. 
  
## <a name="install-skype-for-business-windows-phone-81"></a>Instalar o Skype for Business Windows Phone 8,1

1. Navegue até o [centro de atualizações do Windows Phone 8](https://www.windowsphone.com/en-us/how-to/wp8/update-central) para atualizar seu telefone para o windows phone 8,1.
    
2. Em seu telefone, vá para a **loja**e pesquise pelo **Skype for Business**.
    
3. Toque em **Instalar**. 
    
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Entrar no Skype for Business pela primeira vez

1. Na tela **inicial** , deslize o dedo para a esquerda para exibir seus aplicativos instalados, procure pelo Skype for Business para Windows Phone e, em seguida, toque no ícone para abrir o aplicativo.
    
2. Insira seu endereço de entrada (por exemplo, user@domain.com) e senha e, em seguida, toque em **concluído**.
    
     É provável que você precise informar um nome de usuário e um endereço de entrada. O nome de usuário é o que você usa para entrar na rede da sua organização, seja user@domain.com ou domínio \ nome_de_usuário.
    
3. Na tela **Programa de Aperfeiçoamento da Experiência do Usuário**, toque em **Ingressar** para enviar dados anônimos sobre problemas e utilização do aplicativo à Microsoft, ou **Não, obrigado** se preferir não participar.
    
4. Na tela **Nunca Perder Chamadas de Trabalho**, insira o número do seu celular com os códigos de país e região. Quando o Skype for Business para Windows Phone não pode usar uma rede Wi-Fi ou de dados da rede celular para fazer uma chamada de áudio ou de vídeo, você será automaticamente chamado neste número e conectado à parte de áudio da chamada.
    
5. Toque em **Avançar** e revise as configurações de notificação e acesso ao catálogo telefônico:
    
   - **Notificações por push** Receba um alerta quando receber uma nova mensagem instantânea ou uma nova chamada. Normalmente **Ligado** (recomendado).
    
     > [!IMPORTANT]
     > Se você desativar esta configuração, não será notificado sobre mensagens instantâneas, chamadas ou outros alertas do Skype for Business para Windows Phone, a menos que o aplicativo esteja ativo. 
  
   - **Permitir acesso à agenda telefônica** Procure contatos em seu celular quando você Pesquisar contatos no Skype for Business para Windows Phone.
    
6. Toque em **Avançar** para começar a usar o Skype for Business para Windows Phone.
    
    [Precisa de ajuda para entrar?](https://support.office.com/article/6b827683-ad55-471a-bd4b-3d4ec098bf75)
    
## <a name="verify-mobile-client-installation"></a>Verificar instalação do cliente móvel

Depois de configurar o cliente e entrar com êxito, use os seguintes testes para verificar se a sua instalação do Skype for Business para Windows Phone está funcionando corretamente em seu dispositivo móvel.
  
### <a name="search-for-a-contact-in-the-corporate-directory"></a>Procure um contato no diretório corporativo

1. Na lista de Contatos, toque em **Pesquisar**.
    
2. Procure um contato que conste apenas na lista de endereços global.
    
3. Verifique se o nome do contato aparece nos resultados da pesquisa.
    
### <a name="test-instant-messaging-and-presence"></a>Teste mensagens instantâneas e presença

1. Na lista Contatos, toque em um contato.
    
2. No cartão de visita, toque em mensagens instantâneas (IM) ![Ícone de mensagens instantâneas no Skype for Business](../../media/90f8d5fa-7968-4ef7-bf5b-dddf9b893905.png)Icon.
    
3. Verifique se uma janela de mensagens instantâneas (IM) aparece e se é possível digitar e enviar uma IM.
    
### <a name="test-dial-out-conferencing"></a>Teste a conferência discada

1. No Outlook, agende uma reunião do Skype for Business.
    
2. No seu Windows Phone, abra o convite de reunião.
    
3. Clique no link da reunião para ingressar.
    
4. Atenda à chamada do serviço de conferência e verifique se você está conectado ao áudio da reunião.
    
### <a name="test-push-notifications"></a>Teste as notificações por push

1. Selecione duas contas de usuário diferentes para este teste. 
    
2. No Windows Phone do usuário A, conecte-se ao Skype for Business para Windows Phone com A conta do usuário A.
    
3. Abra outro aplicativo no dispositivo.
    
4. Em um cliente diferente, como o cliente da área de trabalho, conecte-se ao Skype for Business com a conta do usuário B.
    
5. Envie uma mensagem instantânea do usuário B para o usuário A.
    
6. Verifique se a notificação de mensagem instantânea é exibida no dispositivo móvel do usuário A.
    
## <a name="remove-skype-for-business-from-your-windows-phone"></a>Remover o Skype for Business do seu Windows Phone

Para remover o aplicativo Skype for Business para Windows Phone do seu dispositivo móvel: 
  
1. Na tela de início, passe o dedo para ver a lista de aplicativos. 
    
2. Toque e segure o aplicativo Skype for Business para Windows Phone e selecione **desinstalar**.
    


