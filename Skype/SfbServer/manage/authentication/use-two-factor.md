---
title: Usar a autenticação de dois fatores com o cliente Skype for Business e o Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
description: 'Resumo: use a autenticação de dois fatores com o Skype for Business Server e o Skype for Business.'
ms.openlocfilehash: 72ec3570d632eecefd28ebfd0aa50eb70c54ff99
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806531"
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server"></a>Usar a autenticação de dois fatores com o cliente Skype for Business e o Skype for Business Server
 
**Resumo:** Use a autenticação de dois fatores com o Skype for Business Server e o Skype for Business.
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Entrar no Skype for Business pela primeira vez

Suas informações de login geralmente são configuradas automaticamente quando o Skype for Business é instalado. Mas, na primeira vez que usar o Skype for Business, talvez seja preciso iniciar manualmente o cliente.
  
### <a name="to-sign-in-for-the-first-time"></a>Para entrar pela primeira vez

1. Faça logoff na rede da sua organização.
    
2. Selecione **Iniciar todos** os  >  **programas** do Skype for  >  **Business.**
    
    Você deverá ver a tela de login.
    
    - Se a caixa de endereço de login já estiver preenchida, confirme se o endereço mostrado está correto.
    
    - Se não estiver correto ou se a caixa estiver vazia, insira seu endereço de entrada (geralmente é o mesmo que seu endereço de email).
    
    - Se uma caixa de senha vazia for exibida, adicione sua senha.
    
3. Selecione **Entrar.**
    
## <a name="sign-out-of-skype-for-business"></a>Sair do Skype for Business

Quando terminar de usar o Skype for Business, você poderá fechar a exibição, sair da sessão ou sair do programa, tudo no menu Arquivo. A tabela a seguir explica as diferenças nas opções.
  
|**Opção**|**Função**|**Como fazer isso**|
|:-----|:-----|:-----|
|Fechar  <br/> |Fecha sua exibição, mas permite que a sessão do Skype for Business identificada com sua ID de usuário continue a ser executado. Isso é para que você possa continuar a receber notificações e interagir com outras pessoas. <br/> <br/> Você pode obter a exibição a qualquer momento clicando no ícone do Skype for Business na barra de tarefas ou na área de notificação na parte inferior da tela.  <br/> | Na janela principal do Skype for Business, faça o seguinte: <br/> 1. Selecione o **botão Opções** e selecione **Fechar**  >  **Arquivo.**  <br/> 2. Clique **no botão** Fechar (X) no canto superior direito da janela. <br/> |
|Sair  <br/> |Encerra a sessão associada à sua ID de usuário, mas o Skype for Business continua a ser executado em segundo plano. Quando você sair, a janela de login será exibida.  <br/> **Dica:** Selecione **Excluir minhas informações de logon** ao sair para remover o registro de sua ID de logon e senha do computador. Isso pode facilitar o suporte para as pessoas solucionarem problemas de login. Isso também pode ajudar a garantir que suas informações de entrada são mais seguras, tornando difícil para usuários não autorizados fazer logoff com suas credenciais. <br/> |Na janela principal do Skype for Business, selecione o **botão Opções** e, em seguida, **selecione Sair**  >  **do Arquivo.**  <br/> |
|Sair  <br/> |Encerra sua sessão do Skype for Business e desliga o Skype for Business em seu computador. Depois de sair, se quiser reiniciar, selecione **Iniciar** Todos os  >   Programas > Skype for Business. <br/> |Na janela principal do Skype for Business, selecione o **botão Opções** e, em seguida, selecione **Sair do**  >  **Arquivo.**  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a>Entrar no Skype for Business com um cartão inteligente

Algumas organizações agora usam um processo de login em várias etapas, chamado de autenticação de dois fatores, para aumentar a segurança de seus usuários. Se você espera usar essa opção, precisará de um "cartão inteligente" para entrar no Skype for Business. Os cartões inteligentes podem ser físicos ou virtuais:
  
- **Físico** Sobre o tamanho de um cartão de crédito. Você o insere em um leitor de cartão inteligente ao entrar.
    
- **Virtual** Não é um objeto físico, mas um identificador eletrônico que é gravado em um chip especial em seu computador, que em essência cria o cartão inteligente em seu computador. Disponível somente para uso com computadores Windows 8 que contenham o chip TPM (Trusted Platform Module).
    
### <a name="enroll-your-smart-card"></a>Registrar seu cartão inteligente

Antes de poder entrar com um cartão inteligente, o cartão deve ser "inscrito", ou seja, suas credenciais de usuário precisam ser identificadas com o cartão. Esse é o caso, seja o cartão físico ou virtual. Esse processo pode já ter sido executado pelo administrador do Skype for Business Server. Verifique com eles se você não tiver certeza se isso foi feito.
  
> [!NOTE]
> Como cada cartão inteligente virtual está associado apenas ao dispositivo em que está instalado, um cartão separado precisará ser inscrito para cada computador Windows 8 usado. 
  
### <a name="to-manually-enroll-your-smart-card"></a>Para registrar manualmente seu cartão inteligente

1. Faça logoff no computador em que você executará o Skype for Business.
    
2. Usando o Internet Explorer, navegue até a página de Registro da Autoridade de Certificação da sua organização. 
    
    Peça ao administrador do Skype for Business Server o endereço Web desse recurso, caso ainda não o tenha. A URL terá a aparência a seguir: https://MyCA .[ yourcompanyname].com/certsrv.
    
    > [!NOTE]
    > Se você estiver usando o Internet Explorer 10, talvez seja necessário exibir este site no Modo de Compatibilidade. 
  
3. Quando você for solicitado a fazer logoff na página de certificação, faça logoff usando sua conta de domínio (em vez de administrador do computador).
    
4. Na página de boas-vindas do site, selecione **Solicitar um certificado.**
    
5. Selecione **Solicitação Avançada.**
    
6. Selecione **Criar e enviar uma solicitação a essa AC** e clique em **Próximo.**
    
7. Agora você verá uma página chamada Estação de Registro de Cartão Inteligente. Aprove a solicitação para instalar o controle ActiveX e preencha o formulário Solicitação de Certificado Avançado da seguinte maneira:
    
    a. Selecione **o usuário Smartcard** na listada do **Modelo** de Certificado.
    
    b. Selecione **Criar novo conjunto de chaves.**
    
    c. Encontre as informações do fabricante no rótulo do seu cartão inteligente e selecione esse fabricante na lista de lista suspenso do **CSP.**
    
    d. Selecione **CSP** como o Formato de Solicitação, caso ainda não tenha sido selecionado.
    
    e. Selecione **sha1** na lista dropdown do Algoritmo de Hash, caso ainda não tenha sido selecionado.
    
    f. Dê um nome ao certificado que você reconhecerá e clique em **Enviar.**
    
8. Agora insira seu cartão inteligente em branco no leitor de cartão anexado à estação de registro e clique em **Registrar.**
    
9. Quando solicitado, insira seu PIN (número de identificação pessoal) e clique em **OK.**
    
    > [!NOTE]
    > Se a pessoa do suporte técnico não tiver dado um PIN especial a ser usado para registrar seu cartão inteligente, use o valor de PIN de cartão inteligente padrão, que é 12345678. 
  
10. Selecione a opção para forçar o usuário (você) a alterar o PIN na primeira vez que o cartão inteligente for usado.
    
11. Agora insira seu cartão inteligente em branco no leitor de cartão anexado à estação de registro e clique em **Registrar.**
    
12. Quando solicitado, insira seu PIN (número de identificação pessoal) e clique em **OK.**
    
    > [!NOTE]
    > Se a pessoa do suporte técnico não tiver dado um PIN especial a ser usado para registrar seu cartão inteligente, use o valor de PIN de cartão inteligente padrão, que é 12345678. 
  
13. Selecione a opção para forçar o usuário (você) a alterar o PIN na primeira vez que o cartão inteligente for usado.
    
14. Clique **em OK** para confirmar se o certificado exibido tem suas informações.
    
15. Depois de ver o aviso de que o certificado foi emitido, clique **em Instalar esse certificado** para concluir o processo de inscrição.
    
### <a name="sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Entre no Skype for Business com suas credenciais de cartão inteligente

Antes de usar seu cartão inteligente pela primeira vez,  é recomendável que você clique em Excluir minhas informações de login na página de login do Skype for Business. Isso limpa as credenciais de login armazenadas em seu computador e elimina uma possível fonte de erro.
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Para entrar no Skype for Business com suas credenciais de cartão inteligente

1. Inicie o cliente Skype for Business.
    
2. Na tela Entrar, digite seu nome de  conta de usuário na caixa de endereço entrar e clique em **Entrar.**
    
3. Se você estiver usando um cartão inteligente virtual, ignore esta etapa.
    
    Se você estiver usando um cartão inteligente físico, insira o cartão inteligente no leitor de cartão inteligente e será solicitado a fazê-lo e clique em **OK** quando o cartão for detectado.
    
4. Digite o número do PIN para seu cartão inteligente e clique em **OK.**
    
    > [!NOTE]
    > Se você não tiver atribuído um número PIN de cartão inteligente por sua pessoa de suporte, use o valor padrão, que é 12345678. 
  
## <a name="see-also"></a>Confira também

[Gerenciar a autenticação de dois fatores no Skype for Business Server](two-factor-authentication.md)
  
[Configurar a autenticação de dois fatores no Skype for Business Server](configure-two-factor.md)
