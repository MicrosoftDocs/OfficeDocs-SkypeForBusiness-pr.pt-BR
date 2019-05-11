---
title: Usar a autenticação de dois fatores com Skype para o cliente de negócios e Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
description: 'Resumo: Use a autenticação de dois fatores com Skype para Business Server e do Skype para negócios.'
ms.openlocfilehash: c1d67682f229a22f4674e5643ccf8d3a99a59f68
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919455"
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server"></a>Usar a autenticação de dois fatores com Skype para o cliente de negócios e Skype para Business Server
 
**Resumo:** Use a autenticação de dois fatores com Skype para Business Server e do Skype para negócios.
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Entrar no Skype for Business pela primeira vez

Suas informações de entrada geralmente são configuradas automaticamente quando Skype para a empresa está instalado. Mas na primeira vez que você use Skype para a empresa, você pode precisar iniciar manualmente o cliente.
  
### <a name="to-sign-in-for-the-first-time"></a>Para entrar pela primeira vez

1. Faça logon rede da sua organização.
    
2. Selecione **Iniciar** > **todos os programas** > **Skype para negócios**.
    
    Você deverá ver a tela de entrada.
    
    - Se a caixa de endereço de entrada já estiver preenchida, confirme se o endereço mostrado está correto.
    
    - Se ele não está correto ou se a caixa estiver vazia, digite seu endereço de entrada (Isso é geralmente igual a seu endereço de email).
    
    - Se uma caixa de senha vazia for exibida, adicione sua senha.
    
3. Selecione **Entrar**.
    
## <a name="sign-out-of-skype-for-business"></a>Sair do Skype for Business

Quando tiver terminado de uso do Skype for Business, você pode fechar a exibição, sair de sua sessão ou sair do programa, tudo a partir do menu arquivo. A tabela a seguir explica as diferenças nas opções.
  
|**Opção**|**O que ela faz**|**Como executar**|
|:-----|:-----|:-----|
|Fechar  <br/> |Fecha o seu vídeo, mas permite que o Skype para sessão de negócios identificado com seu usuário ID continue em execução. Isso acontece para que você possa continuar a obter notificações e a interagir com outras pessoas. <br/> <br/> Você pode obter a exibição de volta a qualquer momento clicando o Skype para o ícone de negócios na barra de tarefas ou área de notificação na parte inferior da tela.  <br/> | Na Skype para a janela principal de negócios, siga um destes procedimentos: <br/> 1. Selecione o botão **Opções** e selecione o **arquivo** > **Close**.  <br/> 2. Clique no botão **Fechar** (X) no canto superior direito da janela. <br/> |
|Sair  <br/> |Termina a sessão associada com sua ID de usuário, mas Skype para negócios continua a ser executado em segundo plano. Quando você sair, a janela de entrada aparecerá.  <br/> **Dica:** Selecione **Excluir minhas informações de entrada** quando você sair remover o registro de sua ID de logon e senha do computador. Fazer isso torna mais fácil para o pessoal de suporte solucionar problemas de entrada. Também ajuda a garantir que suas informações de entrada fiquem mais seguras ao dificultar que usuários não autorizados façam logon com suas credenciais. <br/> |Na Skype para a janela principal de negócios, selecione o botão **Opções** e selecione o **arquivo** > **Sair**.  <br/> |
|Fechar  <br/> |Encerra a sua Skype para sessão de negócios e desligado Skype for Business no seu computador. Depois de sair, se você deseja reiniciar, selecione **Iniciar** > **Todos os programas** gt _ Skype para negócios. <br/> |Na Skype para a janela principal de negócios, selecione o botão **Opções** e selecione o **arquivo** > **Sair**.  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a>Entrar no Skype for Business com um Cartão Inteligente

Algumas organizações usam um processo de entrada de várias etapas, chamado de autenticação de dois fatores, para aumentar a segurança de seus usuários. Se você estiver esperada para usar essa opção, você precisará de um "cartão inteligente" para entrar no Skype para negócios. Cartões inteligentes pode ser físico ou virtual:
  
- **Físico** Sobre o tamanho de um cartão de crédito. Você o insere em um leitor de cartão inteligente ao fazer logon.
    
- **Virtual** Não é um objeto físico, mas um identificador eletrônico que obtém gravado em um chip especial em seu computador, que basicamente se apoia o cartão inteligente em seu computador. Disponível apenas para uso com computadores Windows 8 que contêm o chip TPM (Trusted Platform Module).
    
### <a name="enroll-your-smart-card"></a>Registrar seu cartão inteligente

Antes de você pode entrar com um cartão inteligente, o cartão deve ser "inscritos" — ou seja, suas credenciais de usuário precisa ser identificados com o cartão. Esse será o caso seja o cartão físico ou virtual. Esse processo talvez já foram transportados saem pelo seu Skype para o administrador do servidor de negócios. Verifique com eles se você não tiver certeza se que tiver sido estabelecida.
  
> [!NOTE]
> Como cada cartão inteligente virtual está associado apenas com o dispositivo está instalado no, será necessário inscritos de cada computador do Windows 8 que você usa um cartão separado. 
  
### <a name="to-manually-enroll-your-smart-card"></a>Para registrar manualmente seu cartão inteligente

1. Faça logon no computador em que você executa Skype for Business no.
    
2. Usando o Internet Explorer, navegue para a página de inscrição de Web de autoridade de certificado da sua organização. 
    
    Peça sua Skype para o administrador do servidor de negócios para o endereço da web deste recurso se ainda não tiver. A URL se parecerá com isto: https://MyCA. [yourcompanyname] .com/certsrv.
    
    > [!NOTE]
    > Se você estiver usando o Internet Explorer 10, você pode precisar exibir este site da Web no modo de compatibilidade. 
  
3. Quando você for solicitado a fazer logon para a página de certificação, faça logon usando sua conta de domínio (em vez de como o administrador do seu computador).
    
4. Na página de Boas-vindas do site, selecione **Solicitar um certificado**.
    
5. Selecione **Solicitação Avançada**.
    
6. Selecione **Criar e enviar uma solicitação para esta CA** e clique em **Avançar**.
    
7. Agora, você verá uma página chamada estação de registro de cartão inteligente. Aprove a solicitação para instalar o controle ActiveX e então preencha o formulário Solicitação de Certificado Avançado desta forma:
    
    a. Selecione **Usuário de cartão inteligente** na lista suspensa **Modelo de Certificado**.
    
    b. Selecione **Criar novo conjunto de chaves**.
    
    c. Localize as informações do fabricante no rótulo do seu cartão inteligente e selecione esse fabricante na lista suspensa **CSP**.
    
    d. Selecione o **CSP** como o formato da solicitação, se ainda não esteja selecionado.
    
    f. Selecione **sha1** na lista suspensa algoritmo de Hash, se ainda não esteja selecionado.
    
    f. Dê o seu certificado um nome que você reconhecerá e clique em **Enviar**.
    
8. Agora insira seu cartão inteligente em branco no leitor de cartão conectado à estação de registro e clique em **Registrar**.
    
9. Quando solicitado, insira seu número de identificação pessoal (PIN) e clique em **OK**.
    
    > [!NOTE]
    > Se o encarregado do suporte técnico não tiver dado um PIN para você registrar seu cartão inteligente, use o valor padrão de PIN de cartão inteligente, 12345678. 
  
10. Selecione a opção para forçar o usuário (você) a alterar o PIN na primeira vez em que o cartão inteligente for usado.
    
11. Agora insira seu cartão inteligente em branco no leitor de cartão conectado à estação de registro e clique em **Registrar**.
    
12. Quando solicitado, insira seu número de identificação pessoal (PIN) e clique em **OK**.
    
    > [!NOTE]
    > Se o encarregado do suporte técnico não tiver dado um PIN para você registrar seu cartão inteligente, use o valor padrão de PIN de cartão inteligente, 12345678. 
  
13. Selecione a opção para forçar o usuário (você) a alterar o PIN na primeira vez em que o cartão inteligente for usado.
    
14. Clique em **OK** para confirmar se o certificado exibido tem suas informações neles.
    
15. Assim que for exibido o aviso de que o certificado foi emitido, clique em **Instalar este certificado** para concluir o processo de registro.
    
### <a name="sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Entrar no Skype for Business com suas credenciais de cartão inteligente

Antes de usar seu cartão inteligente pela primeira vez, é recomendável que você clique em **Excluir minhas informações de entrar** no Skype para a página de entrada corporativos. Fazer isso limpará qualquer credencial de entrada armazenada no computador e eliminará uma possível origem de erros.
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Para entrar no Skype for Business com suas credenciais de cartão inteligente

1. Inicie o Skype para o cliente de negócios.
    
2. Na tela Entrar, digite seu nome de conta de usuário na caixa **Endereço de entrada** e clique em **Entrar**.
    
3. Se você estiver usando um cartão inteligente virtual, ignore esta etapa.
    
    Se estiver usando um cartão inteligente físico, insira o cartão inteligente no leitor de cartão inteligente quando solicitado e então clique em **OK** quando o cartão for detectado.
    
4. Digite o número PIN do seu cartão inteligente e clique em **OK**.
    
    > [!NOTE]
    > Se você não tiver recebido um número PIN de cartão inteligente do pessoal de suporte, use o valor padrão, que é 12345678. 
  
## <a name="see-also"></a>Confira também

[Gerenciar a autenticação de dois fatores no Skype para Business Server](two-factor-authentication.md)
  
[Configurar a autenticação de dois fatores no Skype para Business Server](configure-two-factor.md)
