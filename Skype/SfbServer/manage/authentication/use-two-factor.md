---
title: Usar a autenticação de dois fatores com o cliente Skype for Business e o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
description: 'Resumo: Use a autenticação de dois fatores com o Skype for Business Server e o Skype for Business.'
ms.openlocfilehash: 378b76b61acd004dfe16f04dba922cc2b6fedc83
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818703"
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server"></a>Usar a autenticação de dois fatores com o cliente Skype for Business e o Skype for Business Server
 
**Resumo:** Use a autenticação de dois fatores com o Skype for Business Server e o Skype for Business.
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Entrar no Skype for Business pela primeira vez

Suas informações de entrada geralmente são configuradas automaticamente quando o Skype for Business está instalado. Mas, na primeira vez que você usar o Skype for Business, talvez seja necessário iniciar manualmente o cliente.
  
### <a name="to-sign-in-for-the-first-time"></a>Para entrar pela primeira vez

1. Faça logon na rede da sua organização.
    
2. Selecione **Iniciar** > **todos os programas** > **Skype for Business**.
    
    Você deverá ver a tela de entrada.
    
    - Se a caixa de endereço de entrada já estiver preenchida, confirme se o endereço mostrado está correto.
    
    - Se não estiver correto ou se a caixa estiver vazia, insira seu endereço de entrada (geralmente é o mesmo que o seu endereço de email).
    
    - Se uma caixa de senha vazia for exibida, adicione sua senha.
    
3. Selecione **Entrar**.
    
## <a name="sign-out-of-skype-for-business"></a>Sair do Skype for Business

Quando terminar de usar o Skype for Business, você pode fechar a tela, sair da sessão ou sair do programa, tudo a partir do menu arquivo. A tabela a seguir explica as diferenças nas opções.
  
|**Opção**|**O que ela faz**|**Como executar**|
|:-----|:-----|:-----|
|Fechar  <br/> |Fecha sua tela, mas permite que a sessão do Skype for Business identificada com sua ID de usuário continue sendo executada. Isso acontece para que você possa continuar a obter notificações e a interagir com outras pessoas. <br/> <br/> Você pode retomar a exibição a qualquer momento clicando no ícone do Skype for Business na barra de tarefas ou na área de notificação na parte inferior da tela.  <br/> | Na janela principal do Skype for Business, siga um destes procedimentos: <br/> 1. Selecione o botão **Opções** e, em seguida, selecione **arquivo** > **fechar**.  <br/> 2. Clique no botão **fechar** (X) no canto superior direito da janela. <br/> |
|Sair  <br/> |Finaliza a sessão associada à sua ID de usuário, mas o Skype for Business continua a ser executado em segundo plano. Quando você sair, a janela de entrada aparecerá.  <br/> **Dica:** Selecione **excluir minhas informações de entrada** quando sair para remover o registro da sua ID de logon e senha do computador. Fazer isso torna mais fácil para o pessoal de suporte solucionar problemas de entrada. Também ajuda a garantir que suas informações de entrada fiquem mais seguras ao dificultar que usuários não autorizados façam logon com suas credenciais. <br/> |Na janela principal do Skype for Business, selecione o botão **Opções** e, em seguida, selecione **arquivo** > **sair**.  <br/> |
|Fechar  <br/> |Encerra a sessão do Skype for Business e desliga o Skype for Business no seu computador. Depois de sair, se você quiser reiniciar, selecione **Iniciar** > **todos os programas** > Skype for Business. <br/> |Na janela principal do Skype for Business, selecione o botão **Opções** e, em seguida, selecione **arquivo** > **sair**.  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a>Entrar no Skype for Business com um Cartão Inteligente

Algumas organizações usam um processo de entrada de várias etapas, chamado de autenticação de dois fatores, para aumentar a segurança de seus usuários. Se você espera usar essa opção, precisará de um "cartão inteligente" para entrar no Skype for Business. Os cartões inteligentes podem ser físicos ou virtuais:
  
- **Física** Sobre o tamanho de um cartão de crédito. Você o insere em um leitor de cartão inteligente ao fazer logon.
    
- **Virtual** Não é um objeto físico, mas um identificador eletrônico que é escrito para um chip especial em seu computador, que, em essência, cria o cartão inteligente no seu computador. Disponível somente para uso com computadores com Windows 8 que contenham o chip TPM (Trusted Platform Module).
    
### <a name="enroll-your-smart-card"></a>Registrar seu cartão inteligente

Para que você possa entrar com um cartão inteligente, o cartão deve ser "registrado", ou seja, as credenciais do usuário devem ser identificadas com o cartão. Esse será o caso seja o cartão físico ou virtual. Esse processo já pode ser realizado pelo administrador do Skype for Business Server. Verifique com eles se você não tiver certeza se isso foi feito.
  
> [!NOTE]
> Como cada cartão inteligente virtual está associado somente ao dispositivo em que ele está instalado, um cartão separado precisará ser registrado para cada computador com o Windows 8 que você usar. 
  
### <a name="to-manually-enroll-your-smart-card"></a>Para registrar manualmente seu cartão inteligente

1. Faça logon no computador em que você está executando o Skype for Business.
    
2. Usando o Internet Explorer, navegue até a página de registro na Web de autoridade de certificação da sua organização. 
    
    Peça ao administrador do Skype for Business Server o endereço da Web desse recurso se ainda não o tiver. A URL terá a seguinte aparência: https://MyCA. [nomedesuaempresa]. com/certsrv.
    
    > [!NOTE]
    > Se você estiver usando o Internet Explorer 10, talvez seja necessário exibir este site no modo de compatibilidade. 
  
3. Quando você for solicitado a fazer logon na página de certificação, faça logon usando sua conta de domínio (em vez do administrador do computador).
    
4. Na página de Boas-vindas do site, selecione **Solicitar um certificado**.
    
5. Selecione **Solicitação Avançada**.
    
6. Selecione **Criar e enviar uma solicitação para esta CA** e clique em **Avançar**.
    
7. Agora você verá uma página chamada Estação de registro de cartão inteligente. Aprove a solicitação para instalar o controle ActiveX e então preencha o formulário Solicitação de Certificado Avançado desta forma:
    
    a. Selecione **Usuário de cartão inteligente** na lista suspensa **Modelo de Certificado**.
    
    b. Selecione **Criar novo conjunto de chaves**.
    
    c. Localize as informações do fabricante no rótulo do seu cartão inteligente e selecione esse fabricante na lista suspensa **CSP**.
    
    d. Selecione **CSP** como o formato de solicitação, se ainda não estiver selecionado.
    
    vocálico. Selecione **SHA1** na lista suspensa algoritmo de hash, se ainda não estiver selecionado.
    
    letra. Dê um nome ao seu certificado que você reconheça e clique em **Enviar**.
    
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

Antes de usar o cartão inteligente pela primeira vez, é recomendável clicar em **excluir minhas informações de entrada** na página de entrada do Skype for Business. Fazer isso limpará qualquer credencial de entrada armazenada no computador e eliminará uma possível origem de erros.
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Para entrar no Skype for Business com suas credenciais de cartão inteligente

1. Inicie o cliente Skype for Business.
    
2. Na tela Entrar, digite seu nome de conta de usuário na caixa **Endereço de entrada** e clique em **Entrar**.
    
3. Se você estiver usando um cartão inteligente virtual, ignore esta etapa.
    
    Se estiver usando um cartão inteligente físico, insira o cartão inteligente no leitor de cartão inteligente quando solicitado e então clique em **OK** quando o cartão for detectado.
    
4. Digite o número PIN do seu cartão inteligente e clique em **OK**.
    
    > [!NOTE]
    > Se você não tiver recebido um número PIN de cartão inteligente do pessoal de suporte, use o valor padrão, que é 12345678. 
  
## <a name="see-also"></a>Confira também

[Gerenciar a autenticação de dois fatores no Skype for Business Server](two-factor-authentication.md)
  
[Configurar a autenticação de dois fatores no Skype for Business Server](configure-two-factor.md)
