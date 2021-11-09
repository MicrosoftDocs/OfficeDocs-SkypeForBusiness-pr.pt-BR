---
title: Use a autenticação de dois fatores com Skype for Business cliente e Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
description: 'Resumo: use a autenticação de dois fatores com Skype for Business Server e Skype for Business.'
ms.openlocfilehash: 50237639172a70fdf68e1cca122d74cbf785f68e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60839933"
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server"></a>Use a autenticação de dois fatores com Skype for Business cliente e Skype for Business Server
 
**Resumo:** Use a autenticação de dois fatores com Skype for Business Server e Skype for Business.
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Entre na Skype for Business pela primeira vez

Suas informações de login geralmente são configuradas automaticamente quando Skype for Business é instalada. Mas na primeira vez que você Skype for Business, talvez seja preciso iniciar manualmente o cliente.
  
### <a name="to-sign-in-for-the-first-time"></a>Para entrar pela primeira vez

1. Faça logoff na rede da sua organização.
    
2. Selecione **Iniciar**  >  **Todos os Programas**  >  **Skype for Business**.
    
    Você deve ver a tela de login.
    
    - Se a caixa de endereço de login já estiver preenchida, confirme se o endereço mostrado está correto.
    
    - Se não estiver correto ou se a caixa estiver vazia, insira seu endereço de entrada (geralmente é o mesmo que seu endereço de email).
    
    - Se uma caixa de senha vazia for exibida, adicione sua senha.
    
3. Selecione **Entrar**.
    
## <a name="sign-out-of-skype-for-business"></a>Sair do Skype for Business

Quando terminar de usar Skype for Business, você poderá fechar a exibição, sair da sessão ou sair do programa, tudo no menu Arquivo. A tabela a seguir explica as diferenças nas opções.
  
|**Opção**|**Função**|**Como performá-lo**|
|:-----|:-----|:-----|
|Fechar  <br/> |Fecha sua exibição, mas permite que a sessão Skype for Business identificada com a ID do usuário continue sendo executado. Isso é para que você possa continuar a receber notificações e interagir com outras pessoas. <br/> <br/> Você pode obter a exibição de volta a qualquer momento clicando no ícone Skype for Business na barra de tarefas ou na área de notificação na parte inferior da tela.  <br/> | Na Skype for Business principal, faça um dos seguintes: <br/> 1. Selecione o **botão Opções** e selecione **Fechar**  >  **Arquivo**.  <br/> 2. Clique no **botão Fechar** (X) no canto superior direito da janela. <br/> |
|Sair  <br/> |Encerra a sessão associada à ID do usuário, mas Skype for Business continua sendo executado em segundo plano. Quando você sair, a janela de login aparecerá.  <br/> **Dica:** Selecione **Excluir minhas informações de** logon ao sair para remover o registro da ID de logon e da senha do computador. Isso pode facilitar o suporte às pessoas para solucionar problemas de login. Ele também pode ajudar a garantir que suas informações de entrada são mais seguras, tornando difícil para usuários não autorizados fazer logoff com suas credenciais. <br/> |Na janela Skype for Business principal, selecione **o** botão Opções e selecione **Sair**  >  **do Arquivo**.  <br/> |
|Sair  <br/> |Termina sua Skype for Business e desliga Skype for Business no computador. Depois de sair, se quiser reiniciar, selecione **Iniciar**  >  **Todos os Programas > Skype for Business.** <br/> |Na janela Skype for Business principal, selecione o botão **Opções** e selecione **Saída**  >  **de Arquivo**.  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a>Entre no Skype for Business com um Cartão Inteligente

Algumas organizações agora usam um processo de login em várias etapas, chamado autenticação de dois fatores, para aumentar a segurança de seus usuários. Se você espera usar essa opção, precisará de um "cartão inteligente" para entrar Skype for Business. Os cartões inteligentes podem ser físicos ou virtuais:
  
- **Físico** Sobre o tamanho de um cartão de crédito. Você o insere em um leitor de cartão inteligente quando faz logoff.
    
- **Virtual** Não um objeto físico, mas um identificador eletrônico que é gravado em um chip especial em seu computador, que, em essência, cria o cartão inteligente em seu computador. Disponível apenas para uso com Windows 8 computadores que contenham o chip TPM (Trusted Platform Module).
    
### <a name="enroll-your-smart-card"></a>Registrar seu cartão inteligente

Antes de poder entrar com um cartão inteligente, o cartão deve estar "inscrito", ou seja, suas credenciais de usuário precisam ser identificadas com o cartão. Esse é o caso de o cartão ser físico ou virtual. Esse processo pode já ter sido executado pelo administrador Skype for Business Server usuário. Verifique com eles se você não tem certeza se isso foi feito.
  
> [!NOTE]
> Como cada cartão inteligente virtual está associado apenas ao dispositivo em que está instalado, um cartão separado precisará ser inscrito para cada computador Windows 8 que você usa. 
  
### <a name="to-manually-enroll-your-smart-card"></a>Para registrar manualmente seu cartão inteligente

1. Faça logoff no computador em que você estará executando Skype for Business ligado.
    
2. Usando o Internet Explorer, navegue até a página Registro web de Autoridade de Certificação da sua organização. 
    
    Peça ao Skype for Business Server administrador do Skype for Business Server o endereço da Web desse recurso se você ainda não o tiver. A URL será parecida com esta: https://MyCA .[ yourcompanyname].com/certsrv.
    
    > [!NOTE]
    > Se você estiver usando Internet Explorer 10, talvez seja necessário exibir este site no Modo de Compatibilidade. 
  
3. Quando você for solicitado a fazer logoff na página de certificação, faça logoff usando sua conta de domínio (em vez de como administrador do seu computador).
    
4. Na página de boas-vindas do site, selecione **Solicitar um certificado**.
    
5. Selecione **Solicitação Avançada**.
    
6. Selecione **Criar e enviar uma solicitação para esta CA** e clique em **Próximo**.
    
7. Agora você verá uma página chamada Estação de Registro de Cartão Inteligente. Aprovar a solicitação para instalar o controle ActiveX e, em seguida, concluir o formulário solicitação de certificado avançado da seguinte maneira:
    
    a. Selecione **Usuário smartcard na** lista lista suspenso **Modelo** de Certificado.
    
    b. Selecione **Criar novo conjunto de chaves**.
    
    c. Encontre as informações do fabricante no rótulo do seu cartão inteligente e selecione esse fabricante na lista suspenso **CSP.**
    
    d. Selecione **CSP** como o Formato de Solicitação, se ainda não estiver selecionado.
    
    e. Selecione **sha1** na lista suspenso Algoritmo de Hash, se ainda não estiver selecionado.
    
    f. Dê ao certificado um nome que você reconhecerá e clique em **Enviar**.
    
8. Agora insira seu cartão inteligente em branco no leitor de cartão anexado à estação de registro e clique em **Registrar**.
    
9. Quando solicitado, insira seu PIN (número de identificação pessoal) e clique em **OK**.
    
    > [!NOTE]
    > Se sua pessoa de suporte técnico não tiver lhe dado um PIN especial para usar para registrar seu cartão inteligente, use o valor pin de cartão inteligente padrão, que é 12345678. 
  
10. Selecione a opção para forçar o usuário (você) a alterar o PIN na primeira vez que o cartão inteligente for usado.
    
11. Agora insira seu cartão inteligente em branco no leitor de cartão anexado à estação de registro e clique em **Registrar**.
    
12. Quando solicitado, insira seu PIN (número de identificação pessoal) e clique em **OK**.
    
    > [!NOTE]
    > Se sua pessoa de suporte técnico não tiver lhe dado um PIN especial para usar para registrar seu cartão inteligente, use o valor pin de cartão inteligente padrão, que é 12345678. 
  
13. Selecione a opção para forçar o usuário (você) a alterar o PIN na primeira vez que o cartão inteligente for usado.
    
14. Clique **em OK** para confirmar se o certificado exibido tem suas informações sobre ele.
    
15. Depois de ver o aviso de que o certificado foi emitido, clique em **Instalar esse certificado** para concluir o processo de registro.
    
### <a name="sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Entre no Skype for Business com suas credenciais de cartão inteligente

Antes de usar seu cartão inteligente pela primeira vez,  é recomendável clicar em Excluir minhas informações de login na página de Skype for Business de logom. Isso limpa todas as credenciais de login armazenadas em seu computador e elimina uma possível fonte de erro.
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Para entrar no Skype for Business com suas credenciais de cartão inteligente

1. Inicie o Skype for Business cliente.
    
2. Na tela Entrar, digite o nome da  conta de usuário de login na caixa Endereço de entrar e clique **em Entrar**.
    
3. Se você estiver usando um cartão inteligente virtual, ignore esta etapa.
    
    Se você estiver usando um cartão inteligente físico, insira o cartão inteligente no leitor de cartão inteligente e solicitado a fazer isso e clique em **OK** quando o cartão for detectado.
    
4. Digite o número de PIN que você tem para seu cartão inteligente e clique em **OK**.
    
    > [!NOTE]
    > Se você não tiver um número pin de cartão inteligente atribuído pela pessoa de suporte, use o valor padrão, que é 12345678. 
  
## <a name="see-also"></a>Confira também

[Gerenciar a autenticação de dois fatores Skype for Business Server](two-factor-authentication.md)
  
[Configurar a autenticação de dois fatores Skype for Business Server](configure-two-factor.md)
