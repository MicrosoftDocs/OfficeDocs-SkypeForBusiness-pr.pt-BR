---
title: Mover usuários locais para Skype para negócios Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 2475674a-f592-4fa8-ae99-f71cbea54dc0
description: 'Resumo: Informações sobre como mover usuários locais para Skype para negócios Online.'
ms.openlocfilehash: 9aa4c87d713af437f1fbb81cd23e354792559aa8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="move-on-premises-users-to-skype-for-business-online"></a>Mover usuários locais para Skype para negócios Online
 
**Resumo:** Informações sobre como mover os usuários locais para Skype para negócios Online.
  
> [!CAUTION]
> Os dispositivos Lync Phone Edition DEVEM ser atualizados para o firmware mínimo necessário em seu ambiente local antes de mover para o Skype for Business Online. Se você mover seus usuários da implantação local para a online antes de atualizar o firmware, eles não conseguirão se conectar usando os seus telefones. Para corrigir esse problema, os usuários devem ser movidos de volta para o ambiente local para que seus telefones sejam atualizados para o firmware mínimo. NÃO TENTE ATUALIZAR PARA O FIRMWARE MÍNIMO OU FAZER A REINICIALIZAÇÃO FORÇADA DO TELEFONE ANTES DE MOVER O USUÁRIO DE VOLTA PARA SEU AMBIENTE LOCAL.
Se houver uma reinicialização forçada enquanto o dispositivo não estiver no firmware mínimo, o padrão será definido como Autenticação PIN, que não tem suporte no Skype for Business Online. Para obter mais informações, consulte [Getting telefones para Skype para negócios Online](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).
  
Esta é uma etapa opcional que é necessária apenas se você estiver movendo usuários locais para Skype para negócios Online. Antes de começar mover usuários para Skype para Business Online, verifique se o Skype para Business Online Connector (módulo do Windows PowerShell) é implantado em seus servidores Front-End. Se não for, você pode baixá-lo no [Centro de download](https://www.microsoft.com/en-us/download/details.aspx?id=39366)da. Além disso, para preparar seu AD, será necessário configurar o Azure AD Connect. A versão do AAD Connect que você usar deve ser a versão 1.0.9125.0 ou posterior. Se você estiver usando uma versão anterior das ferramentas do AAD Connect ou do DirSync, atualize para a versão com suporte. Você pode atualizar sua instalação atual e manter qualquer regra personalizada que você tenha definido em seu ambiente.
  
Mover usuários usando um dos Skype para painel de controle do Business Server ou Skype para Business Server Management Shell em sua implantação no local, mas você deve ter credenciais de administrador para a sua implantação do Office 365.
  
## <a name="moving-users-by-using-skype-for-business-control-panel"></a>Movendo usuários usando o Skype para painel de controle de negócios

### <a name="to-move-a-user-to-skype-for-business-online"></a>Para mover um usuário para Skype para negócios Online

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou csadministrator, faça logon em qualquer computador em sua implantação interna que tem Skype para Business Server ou, no mínimo Skype para as ferramentas de administração de servidor de negócios instaladas.
    
2. No menu Iniciar ou atalho da área de trabalho, abra o Skype para painel de controle do servidor de negócios.
    
    Você também pode acessar o Skype para painel de controle do Business Server usando a URL do administrador, se você tiver configurado um.
    
3. Na barra de navegação esquerda, clique em **Usuários**.
    
4. Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.
    
5. Clique no usuário, no menu de **Ação** e, em seguida, clique em **Mover usuários selecionados para o Skype for Business Online**.
    
6. Na página **Mover usuários para o Skype for Business Online**, leia as informações e clique em **Avançar**.
    
7. Na próxima página, se não você ainda estiver conectado ao Office 365, clique em **entrar no Office 365**, forneça suas credenciais e clique em **Okey** e em **Avançar**.
    
8. Verifique se o número de usuários a serem movidos está correto e clique em **Avançar**.
    
9. Na próxima página, confira os resultados e clique em **Fechar**.
    
## <a name="moving-users-by-using-skype-for-business-server-management-shell"></a>Movendo usuários usando o Skype do Shell de gerenciamento do servidor de negócios

Para mover um usuário local para seu Skype para locatário Business Online, execute os cmdlets a seguir no Skype do Shell de gerenciamento do servidor de negócios, utilizando as credenciais de administrador para o seu locatário do Microsoft Office 365. Substitua "username@contoso.com" pela informação do usuário que você deseja mover.
  
```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
```

O formato da URL especificado para o parâmetro **HostedMigrationOverrideUrl** deve ser a URL para o pool de onde o serviço de migração hospedado estiver em execução, no seguinte formato: _Https://\<FQDN do Pool\>/HostedMigration/ hostedmigrationService.svc_.
  
Você pode determinar a URL para o serviço de migração hospedado, exibindo a URL para o Skype para centro de administração de on-line de negócios para sua conta de locatário do Office 365.
  
> [!NOTE]
> A URL é sensível a letras maiúsculas e minúsculas. 
  
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>Para identificar a URL do Serviço de Migração Hospedada do seu locatário do Office 365

1. Faça logon no seu inquilino do Office 365 como um administrador.
    
2. Abra o **Centro de administração do Skype for Business**.
    
3. Com o **Centro de administração do Skype for Business** exibido, selecione e copie a URL na barra de endereço no **lync.com**. Uma URL de exemplo seria parecida com esta:
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. Substitua **webdir** na URL por **admin**, o que resulta no seguinte: 
    
     `https://admin0a.online.lync.com`
    
5. Anexe a cadeia de caracteres a seguir à URL: **/HostedMigration/hostedmigrationService.svc**.
    
    A URL resultante, que é o valor do **HostedMigrationOverrideUrl**, deve se parecer com o seguinte:
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationService.svc`
    

