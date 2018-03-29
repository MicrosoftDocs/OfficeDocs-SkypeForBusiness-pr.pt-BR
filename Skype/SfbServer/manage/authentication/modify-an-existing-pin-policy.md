---
title: Modificar uma política de PIN existente no Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 517caaee-3349-4fa6-8d86-e4da3258a445
description: 'Resumo: Modificar uma política PIN existente no Skype para Business Server 2015.'
ms.openlocfilehash: bb9be5807da0e72dfbc59d2000af82b181bfc6d6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="modify-an-existing-pin-policy-in-skype-for-business-server-2015"></a>Modificar uma política de PIN existente no Skype for Business Server 2015
 
**Resumo:** Modificar uma política PIN existente no Skype para Business Server 2015.
  
Você pode usar a guia **Política de PIN** para fornecer autenticação de (PIN) número de identificação pessoal para usuários que estão se conectando ao Skype for Business com telefones IP. Para usar a autenticação PIN, certifique-se de que **Habilitar Autenticação PIN** esteja selecionado nas configurações do Web Service.
  
Siga estas etapas para modificar uma política de PIN no nível de usuário ou local. 
  
### <a name="to-modify-an-existing-pin-policy"></a>Para modificar uma política de PIN existente

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server 2015.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 
    
3. Na barra de navegação à esquerda, clique em **Segurança** e em **Política de PIN**.
    
4. Na página **Política de PIN**, clique em uma política, clique em **Editar** e clique em **Mostrar detalhes**.
    
5. Em **Editar Política de PIN**, em **Comprimento mínimo do PIN**, digite ou selecione o comprimento mínimo do PIN que você deseja permitir. O comprimento mínimo padrão é de cinco dígitos.
    
6. Para poder especificar o número máximo de tentativas de logon antes que um usuário seja bloqueado, marque a caixa de seleção **Especificar o máximo de tentativas de logon**. Se você não selecionar essa opção, o número máximo de tentativas permitidas será determinado automaticamente com base no tamanho do PIN. Por padrão, o número máximo de tentativas é determinado automaticamente.
    
7. Se você marcou a caixa de seleção **Especificar o máximo de tentativas de logon**, em **Máximo de tentativas de logon**, digite ou selecione o número máximo de tentativas de logon que você deseja permitir.
    
8. Para fazer com que os PINs expirem, marque a caixa de seleção **Habilitar validade do PIN**. Se você não selecionar essa opção, os PINs nunca expirarão. Por padrão, os PINs nunca expiram.
    
9. Se você marcou a caixa de seleção **Habilitar validade do PIN**, em **O PIN expira após (dias)**, digite ou selecione o número de dias após o qual o PIN expirará.
    
10. Em **Contagem do histórico de PINs**, digite o número de PINs que um usuário precisa criar antes de poder reutilizar um PIN. Por padrão, os usuários podem reutilizar seus PINs.
    
11. Para permitir padrões comuns de dígitos nos PINs, como números sequenciais e conjuntos repetitivos de números, marque a caixa de seleção **Permitir padrões comuns**. Se você não selecionar essa opção, somente os padrões complexos de dígitos serão permitidos. Por padrão, somente os padrões complexos de dígitos são permitidos.
    
    > [!IMPORTANT]
    > Recomendamos que você não permita os padrões comuns. 
  
12. Clique em **Confirmar**.
    

