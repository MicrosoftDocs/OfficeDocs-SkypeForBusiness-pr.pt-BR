---
title: Criar uma nova política de PIN no Skype for Business Server
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
ms.assetid: 8bdf0478-fe9f-4371-93ff-db39381a25db
description: 'Resumo: crie uma nova política de PIN Skype for Business Server.'
ms.openlocfilehash: cf9a35c634c9b53b557601009fa131c3c24e7db2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844204"
---
# <a name="create-a-new-pin-policy-in-skype-for-business-server"></a>Criar uma nova política de PIN no Skype for Business Server
 
**Resumo:** Crie uma nova política de PIN Skype for Business Server.
  
Você pode usar a **página Política de PIN** para fornecer autenticação de número de identificação pessoal (PIN) aos usuários que estão se conectando Skype for Business com telefones IP. Para usar a autenticação PIN, certifique-se de que **Habilitar Autenticação PIN** esteja selecionado nas configurações do Web Service.
  
Siga estas etapas para criar uma política de PIN de nível de usuário ou de nível de site. 
  
### <a name="to-create-a-user-or-site-pin-policy"></a>Para criar uma política de PIN de usuário ou de site

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou Skype for Business Server.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 
    
3. Na barra de navegação à esquerda, clique em **Segurança** e em **Política de PIN**.
    
4. Na página **Política de PIN**, clique em **Novo** e execute um dos seguintes procedimentos:
    
   - Para criar uma política de nível de usuário, clique em **Política de usuário**. Em **Nova Política de PIN**, em **Nome**, digite um nome que descreva a política.
    
   - Para criar uma política de nível de site, clique em **Política de site**. No campo de pesquisa **Selecione um Site**, digite todo ou parte do nome do site para o qual deseja criar uma política. Na lista resultante de sites, clique naquele que deseja e em **OK**.
    
5. No campo **Descrição**, digite uma descrição para a política de PIN.
    
6. No campo **Tamanho mínimo do PIN**, digite ou selecione o tamanho mínimo do PIN que você deseja permitir. O tamanho mínimo padrão é de cinco dígitos.
    
7. Para poder especificar o número máximo de tentativas de logon antes que um usuário seja bloqueado, marque a caixa de seleção **Especificar o máximo de tentativas de logon** . Se você não selecionar essa opção, o número máximo de tentativas permitidas será determinado automaticamente com base no tamanho do PIN. Por padrão, o número máximo de tentativas é determinado automaticamente.
    
8. Se você marcou a caixa de seleção **Especificar o máximo de tentativas de logon**, em **Máximo de tentativas de logon**, digite ou selecione o número máximo de tentativas de logon que você deseja permitir.
    
9. Para fazer com que os PINs expirem, marque a caixa de seleção **Habilitar validade do PIN**. Se você não selecionar essa opção, os PINs nunca expirarão. Por padrão, os PINs nunca expiram.
    
10. Se você marcou a caixa de seleção **Habilitar validade do PIN**, em **O PIN expira após (dias)**, digite ou selecione o número de dias após o qual o PIN expirará.
    
11. Em **Contagem do histórico de PINs**, digite o número de PINs que um usuário precisa criar antes de poder reutilizar um PIN. Por padrão, os usuários podem reutilizar seus PINs.
    
12. Para permitir padrões comuns de dígitos em PINs, como "1234" e "8888", marque a caixa de seleção Permitir **padrões** comuns. Se você não selecionar essa opção, somente os padrões complexos de dígitos serão permitidos. Por padrão, somente os padrões complexos de dígitos são permitidos.
    
    > [!IMPORTANT]
    > Recomendamos que você não permita os padrões comuns. 
  
13. Clique em **Confirmar**.
    

