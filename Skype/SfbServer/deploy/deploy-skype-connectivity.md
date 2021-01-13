---
title: Implantar a Conectividade Skype no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 'Resumo: saiba como conectar o Skype for Business Server ao consumidor do Skype. Também conhecido como conectividade Skype.'
ms.openlocfilehash: ae3982375c0693c34e204e4512481a1f9f3b6ec3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834101"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>Implantar a Conectividade Skype no Skype for Business Server

**Resumo:** Saiba como conectar o Skype for Business Server ao consumidor do Skype. Também conhecido como conectividade Skype.
  
Este artigo apresenta a implantação da Conectividade Skype.
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Visão geral de conectividade do Skype para profissionais de TI

A Conectividade Skype oferece aos usuários do Skype for Business a capacidade de pesquisar e adicionar usuários do Skype. A Conectividade Skype é um recurso do Skype for Business que permite habilitar a federação e a pesquisa de diretórios com usuários do Skype. Depois de habilitar a Conectividade Skype, os usuários do Skype for Business poderão pesquisar e adicionar usuários do Skype.
  
## <a name="skype-directory-search"></a>Pesquisa de Diretório do Skype

A funcionalidade de Pesquisa de Diretório do Skype oferece aos usuários do Skype for Business a capacidade de pesquisar contatos do Skype. A funcionalidade de pesquisa permite que os usuários pesquisem usando o seguinte:
  
- **Pesquisa por nome de exibição, exemplo "John Doe"** - Isso pode retornar muitos resultados, portanto, talvez você não encontre o que está procurando.
    
- **Pesquisa por nome de exibição mais local, exemplo "John Doe in Timea"** - Isso reduzirá consideravelmente os resultados da pesquisa.
    
- **Pesquisar por email, exemplo "johndoe@outlook.com"** - Isso deve retornar um resultado na maioria dos casos; que corresponde exatamente ao email especificado. Mas se o mesmo email estiver associado a mais de uma conta, vários resultados poderão ser retornados.
    
- **Pesquisa por número de telefone, exemplo "123-123-1234"** - Isso deve retornar um resultado na maioria dos casos; que corresponde exatamente ao telefone especificado. O número de telefone deve incluir o código do país (ou seja, 1-xxx-yyy-zzzz). Se o mesmo número de telefone estiver associado a mais de uma conta, vários resultados poderão ser retornados.
    
- **Pesquisa por Nome do Skype, exemplo "JohnDoe1456"** - Se uma combinação exata for encontrada, ela será retornada como o primeiro resultado. Outras possíveis combinações de "nome" podem ser retornadas.
    
    > [!NOTE]
    > A Pesquisa de Diretório do Skype deve ser capaz de se comunicar com os seguintes endereços IP na porta 443: 104.40.75.246, 23.101.135.34 e 40.113.86.19. 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Matriz de implantação suportada para a Pesquisa de Diretório do Skype

A tabela a seguir descreve o suporte para a Pesquisa de Diretório do Skype.
  

||**Front-end do Skype for Business Server**|**Front End do Lync Server 2013 (ou mais antigo)**|**Comments**|
|:-----|:-----|:-----|:-----|
|Borda do Skype for Business Server  <br/> |Com suporte  <br/> |Não Suportado  <br/> |O Skype for Business Server e o Edge são pré-requisitos para a Pesquisa de Diretório do Skype  <br/> |
|Borda do Skype for Business Server + Borda do Lync Server 2013 implantada lado a lado  <br/> |Com suporte  <br/> |Não Suportado  <br/> |O tráfego da Pesquisa de Diretórios do Skype flui através dos servidores de Borda do Skype for Business Server. O tráfego de federação passa pela borda configurada pelo administrador. Por exemplo, o administrador pode optar por continuar a enviar tráfego de federação através de servidores de Borda do Lync Server 2013 que não suportam a Pesquisa de Diretório do Skype.  <br/> |
|Borda do Lync Server 2013 (ou mais antiga)  <br/> |Não Suportado  <br/> |Não Suportado  <br/> ||
   
> [!NOTE]
> O serviço de addressbook em execução no Front End do Skype for Business Server encontra a Borda pela existência da porta de Pesquisa do Skype 4443 no servidor de Borda. 
  
> [!NOTE]
> Caso um cliente tenha vários sites em sua implantação local e tenha implantado apenas um servidor/pool de Borda do Skype for Business Server, o tráfego de pesquisa de todos os sites passará pelo único servidor de Borda disponível. O administrador precisa garantir que os pools de todos os sites possam acessar o pool/servidor de Borda do Skype for Business Server implantado. 
  
> [!NOTE]
> O serviço de gráfico do Skype acelerará as solicitações de pesquisa de qualquer cliente local ou do Microsoft 365 ou Office 365 se a taxa de solicitações exceder 15 solicitações/segundo. 
  
> [!NOTE]
> Para clientes de grandes empresas locais, os domínios precisarão estar na lista branca com o serviço de pesquisa do Skype para permitir taxas de solicitação maiores. 
  
> [!NOTE]
> O Skype for Business Server acelerará as solicitações de entrada, se houver muitas solicitações pendentes na fila. 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online"></a>Implantando a Conectividade Skype para o Skype for Business Online

A Conectividade Skype também é um recurso do Skype for Business Online, que faz parte do Microsoft 365 e office 365. Você pode habilitar o recurso Conectividade Skype no Centro de Administração do Skype for Business no Centro de administração do Microsoft 365.
  
Para Microsoft 365 Midsize Business, Office 365 Enterprise, Microsoft 365 Education e Office 365 for Government: entre no centro de administração do Microsoft 365 e navegue até o Centro de Administração do Skype for Business. Vá para Comunicações Externas. Em Provedores de Serviços Públicos de IM, clique em Habilitar. Se você quiser controlar o acesso de usuários individuais à Conectividade Skype, poderá fazer isso editando as configurações de Comunicações Externas de usuários individuais.
  
Para o Office 365 Small Business Premium: entre no Office 365 e vá para Mensagens instantâneas, reuniões e conferências de Configurações do Serviço \> \> de Administração. Ativar comunicações externas. A opção De comunicações externas liga a Conectividade Skype e as comunicações com outras organizações que usam o Skype for Business.
  
Para obter mais informações sobre a administração do Skype for Business Online, consulte:
  
- [Permitir que os usuários entrem em contato com usuários externos do Skype for Business](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [O que tentar se você não conseguir mensagens de contatos externos do Skype for Business ou do Skype](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [Adicionar um contato no Skype for Business](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [Administradores: Definir as configurações do Skype for Business para usuários individuais](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>Implantando a conectividade Skype para o Skype for Business Server

O Skype for Business Server usa a arquitetura de acesso de federação para dar suporte à conectividade com o Skype. Essa conectividade permite que os usuários do Skype for Business Server adicionem o Skype. Os clientes do Skype também podem adicionar usuários do Skype for Business à sua lista de contatos. Com base nas políticas definidas administrativamente no Skype for Business Server, os usuários poderão se comunicar usando mensagens instantâneas, ver a presença uns dos outros e iniciar chamadas de áudio e vídeo. A conectividade Skype também é um recurso do Skype for Business Online e pode ser habilitada para clientes do Skype for Business Online a partir do Centro de Administração do Skype for Business no centro de administração do Microsoft 365.
  
> [!NOTE]
> Se o Skype for Business Server já estiver configurado para se conectar ao Windows Messenger usando a PIC (Conectividade Pública de Mensagens Instantâneas), sua implantação já está configurada para conectividade do Skype. A única alteração que você pode considerar é renomear sua entrada de PIC existente no Messenger como Skype. 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>O site de provisionamento de conectividade de IM pública do Skype for Business Server não está mais disponível

O site usado anteriormente para provisionar manualmente a federação entre implantações locais do Skype for Business e o Skype não é mais necessário e será desligado em 15/8/2019. A federação com o Skype agora utiliza a descoberta de parceiros federados, que é o mesmo mecanismo necessário para federação com o Skype for Business Online.

A comunicação entre qualquer implantação local do Skype for Business e os usuários do Skype por meio da infraestrutura de IM pública existente agora exige que a configuração do Servidor de Borda local seja compatível com o Skype for Business Online.

> [!NOTE]
> Nenhuma ação é necessária para a maioria dos clientes, incluindo todas as implantações federadas com o Skype for Business Online.
  
As implantações locais são necessárias para publicar um registro SRV dns de federação para cada domínio que hospedam. As diretrizes estão disponíveis no [planejamento de DNS.](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning) Cada domínio deve ser resolvido pela consulta SRV dns para um FQDN de servidor de borda que satisfaça uma combinação de sufixo de nível superior do domínio. Por exemplo, considere o domínio "contoso.com":

|**FQDNs válidos**|**Comentário**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |Em cada caso, o FQDN exato deve estar presente no SN ou no SAN do certificado externo instalado no servidor de borda.   |
|access.contoso.com   ||
|**FQDNs inválidos**|**Motivo**|
|sip.contoso-edge.com   |Não é uma combinação de sufixos.  |
|sip.it.contoso.com   |Não é uma combinação de sufixo de nível superior.   |

Mais orientações sobre certificados externos podem ser encontradas no [planejamento de certificados.](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning)

#### <a name="faqs"></a>Perguntas Frequentes

**Por que o site de provisionamento está sendo desligado?**
O mecanismo de provisionamento de IM (PIC) público (pic.lync.com) que foi implantado em 2006 não é mais serviceável e será desligado em 15/8/2019. Em vez disso, a federação de IM pública assumirá o mesmo modelo de federação usado pelo Skype for Business Online, conhecido como "descoberta de parceiros", pelo qual uma implantação local pode ser descoberta publicamente por seus registros DNS SRV de federação.

**Essa alteração significa que a federação de IM pública está sendo preterida?**
Não. A federação de IM pública continuará a ter suporte por muitos anos, provavelmente até que o produto local do Skype for Business atinja o fim da vida útil.

**Nossa empresa tem uma relação híbrida (espaço de endereço compartilhado) com o Skype for Business Online, estamos sendo afetadas?**
Não, como você já está federando com o Skype for Business Online, essa alteração não o afetará.
 
**Essa alteração significa que nossa empresa precisa habilitar a federação com o Skype for Business Online?**
Não. Se as configurações de proxy do servidor de borda não habilitar a federação com o provedor de hospedagem do Skype for Business Online (sipfed.online.lync.com), essa alteração não afetará isso. No entanto, os mesmos requisitos de DNS e certificado que se aplicam à federação com o Skype for Business Online agora também se aplicam à federação com usuários do Skype.
 
**Nossa empresa é grande e não pode alterar sua configuração de borda devido a razões regulatórias/conformidade/etc... o que podemos fazer?**
Qualquer organização local que não possa alterar sua configuração de servidor de borda conforme especificado deve falar com o suporte ao produto no momento mais cedo.

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>Habilitando a federação e a pic (conectividade de IM pública)

Agora, concentre-se no ambiente do Skype for Business Server e nas tarefas administrativas necessárias para configurar a Conectividade Skype. Nesta seção, presumimos que o administrador implantou o Skype for Business Server e configurou o acesso externo, também conhecido como servidores de Borda. 
  
Há três etapas principais necessárias para habilitar a federação e a PIC. São eles:
  
1. Configurar Federação e PIC
    
2. Configurar pelo menos uma política para dar suporte ao acesso de usuário federado
    
3. Definir a configuração do provedor de PIC do Skype
    
#### <a name="1-configure-federation-and-pic"></a>1. Configurar Federação e PIC

A federação é necessária para permitir que os usuários do Skype se comuniquem com usuários do Skype for Business em sua organização. A PIC (Conectividade Pública de Mensagens Instantâneas) é uma classe de federação e deve ser configurada para permitir que os usuários do Skype for Business se comuniquem com usuários do Skype. A federação e a PIC são configuradas usando o Painel de Controle do Skype for Business Server.
  
> [!NOTE]
> A federação de PIC não é mais suportada por versões de produto anteriores ao Lync Server 2010 (Live Communication Server, Office Communications Server). As plataformas com suporte para federação de PIC incluem Skype for Business Server, Lync Server 2013 e Lync Server 2010. 
  
A federação é necessária para permitir que os usuários do Skype se comuniquem com usuários do Skype for Business em sua organização. A PIC (Conectividade Pública de Mensagens Instantâneas) é uma classe de federação e deve ser configurada para permitir que os usuários do Skype for Business Server se comuniquem com usuários do Skype. A federação e a PIC são configuradas usando a caixa de diálogo de configuração de Borda do Painel de Controle do Skype for Business Server, conforme mostrado na figura.
  
![Definir Novo Pool de Borda](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> Os atributos EnableSkypeIdRouting e EnableSkypeDirectorySearch precisam ser definidos como true nas configurações do provedor público (consulte as instruções posteriores) para que a Pesquisa funcione. 
  
Isso conclui as tarefas administrativas que devem ser executadas no servidor. Agora você está pronto para a Conectividade Skype.
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. Configure pelo menos uma política para suportar o acesso de usuário federado

Usando o Painel de Controle do Skype for Business Server, um administrador deve configurar uma ou mais políticas de acesso de usuário externo para controlar se os usuários do Skype podem colaborar com usuários internos do Skype for Business Server.
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. Definir a configuração do provedor de PIC do Skype

Usando o Shell de Gerenciamento do Skype for Business Server, um administrador deve configurar a política de cliente do Skype for Business para exibir o Skype como um provedor de PIC adicional. 
  
> [!NOTE]
> Os usuários dos provedores de serviços de PIC (Conectividade Pública de Mensagens Instantâneas) não poderão participar de mensagens instantâneas ou conferências em sua organização até que você também configure pelo menos uma política (etapa 2, anteriormente neste procedimento) para suportar a conectividade a redes públicas de mensagens instantâneas. 
  
Para novas instalações, você pode configurar a Conectividade Skype habilitando um Provedor Público do Skype usando o Painel de Controle do Skype for Business Server, conforme mostrado na figura.
  
![Provedores Federados SIP](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> Para configurar a Conectividade Skype ao atualizar para o Skype for Business Server, você deve remover e adicionar o provedor público existente do Skype. 
  
A configuração da Conectividade Skype também pode ser feita usando apenas o PowerShell. Para configurar a Conectividade Skype usando o PowerShell:
  
1. Em um servidor front-end do Skype for Business Server, abra o Shell de Gerenciamento do Skype for Business Server.
    
2. Execute os dois comandos a seguir:
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > Se você ainda não tiver um provedor de PIC em seu ambiente e estiver criando um novo provedor de PIC, não será necessário executar o cmdlet Remove-CsPublicProvider usuário. 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    O que os parâmetros menos óbvios fazem?
    
   - ProxyFqdn: local da borda de federação do Skype (de propriedade/mantida pela Microsoft)
    
   - IconURL: ícone usado pelo cliente Skype for Business do Lync &amp; para identificar visualmente os contatos do Skype
    
   - NameDecorationRoutingDomain e NameDecorationExcludedDomainList: a configuração permite que os usuários insiram os MSAs dos usuários do Skype sem precisar saber mais sobre como "decorar" domínios que não são da Microsoft com "msn.com". Isso elimina a necessidade de digitar "user(contoso.com)@msn.com" para todos os domínios que NÃO estão em ExcludedDomainList. O cliente SfB formatará automaticamente o MSA se o domínio NÃO estiver na lista excluído. Adicionamos os domínios de conta da Microsoft mais comuns à lista excluída.
    
     > [!NOTE]
     > O Provedor Público deve ser removido e adicionado novo caso sejam feitas alterações. Nenhuma alteração local é permitida. 
  
     > [!NOTE]
     > Adicionado no cliente de área de trabalho do Lync Server 2013 CU5 &amp; Lync no Office 2013 SP1, o NameDecorationRoutingDomain e o NameDecorationExcludedDomainList melhoram a situação em que os usuários do Lync que adicionam contatos do Skype precisam "decorar" domínios que não são da Microsoft para identificá-los e encaminhá-los ao Skype (o formato de: user(contoso.com)@msn.com). Essas novas configurações permitirão a formatação automática do endereço do usuário na caixa de diálogo "Adicionar contato do Skype" com o NameDecorationRoutingDomain (que deve ser definido como msn.com) se ele não contiver os domínios em NameDecorationExcludedDomainList (atualmente, podemos dar suporte a msn.com, live.com, Hotmail.com, outlook.com). 
  
3. A partir de um cliente Skype for Business, os usuários agora podem pesquisar e adicionar um usuário do Skype.
    
## <a name="clients-and-interoperability-matrix"></a>Clientes e matriz de interoperabilidade

A tabela a seguir descreve o status de interop entre a versão mais recente do consumidor do Skype e a versão mais recente do Skype for Business.
  

|**Clientes Skype**|**Adicionar contatos, mensagens im, presença, áudio e chamada de vídeo**|**Comentário**|
|:-----|:-----|:-----|
|Skype Windows Desktop  <br/> |7.6 ou superior, Windows XP e superior  <br/> |**NOVO:** suporte adicionado para o cliente Skype do Windows em execução no Windows XP e no Windows Vista (requer a versão mais recente do cliente **7.26 ou superior)** <br/> |
|Skype Mobile - Telefone e Tablet Android  <br/> |6.19 ou superior, executando o sistema operacional Android versão 4.0.3 ou superior  <br/> |Dispositivos de baixa especificação podem não suportar a chamada de vídeo  <br/> |
|Skype Mobile - iOS  <br/> |6.11 ou superior, no IOS 7 ou superior  <br/> |Não há suporte para iPhone 4 e versões anteriores, iPod 4ª geração e versões anteriores, iPad de 1ª geração  <br/> |
|Skype Mac  <br/> |7.19 ou superior, no Mac OS X 10.9 (Dallass) ou superior  <br/> |Requer o Mac OSX 10.9 ou superior  <br/> |
|Skype Universal Windows App (Windows 10) Desktop e Mobile  <br/> |Windows 10 (Redstone 1 update ou posterior)  <br/> |O Aplicativo Universal do Windows receberá atualização no segundo ano de 2016 adicionando suporte à interop  <br/> |
   
A tabela a seguir descreve o status de interop entre a versão mais recente do Skype for Business e a versão mais recente do consumidor do Skype. 
  
|**Cliente**|**Pesquisar e Adicionar Contatos do Diretório do Skype**|**Skype A/V, interop de IM**|
|:-----|:-----|:-----|
|Skype for Business  <br/> |Sim  <br/> |Sim  <br/> |
|Skype for Business no Mac  <br/> |Pode adicionar (sem pesquisa)  <br/> |Sim  <br/> |
|Lync Desktop 2013  <br/> |Pode adicionar (sem pesquisa)  <br/> |Sim  <br/> |
|Lync Web App – online e local  <br/> |N/D  <br/> |N/D  <br/> |
|Lync Mobile - Windows Phone  <br/> |Em breve  <br/> |Sim  <br/> |
|Lync Mobile - Android  <br/> |Em breve  <br/> |Sim  <br/> |
|Lync Mobile - iOS  <br/> |Em breve  <br/> |Sim  <br/> |
|Sistema de salas do Lync  <br/> |Em breve  <br/> |Sim  <br/> |
|Lync Modern App (Win 8.1)  <br/> |Sim  <br/> |Sim  <br/> |
|Lync Mac 2011  <br/> |Pode adicionar (sem pesquisa)  <br/> |Sim  <br/> |
|Lync Desktop 2010  <br/> |Pode adicionar (sem pesquisa)  <br/> |Sim  <br/> |
|Lync Phone Edition  <br/> |N/D  <br/> |N/D  <br/> |
|Lync Attendant  <br/> |N/D  <br/> |N/D  <br/> |
   
