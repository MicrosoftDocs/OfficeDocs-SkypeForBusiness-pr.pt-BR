---
title: Implantar Skype conectividade no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 'Resumo: saiba como se conectar Skype for Business Server com Skype consumidor. Também conhecido como Skype conectividade.'
ms.openlocfilehash: 003e9a69dc4213b662795b0570afb3ca152d7e00
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60751300"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>Implantar Skype conectividade no Skype for Business Server

**Resumo:** Saiba como se conectar Skype for Business Server com Skype consumidor. Também conhecido como Skype conectividade.
  
Este artigo orienta a implantação para Skype Conectividade.
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Skype Visão geral da conectividade para profissionais de TI

Skype A conectividade fornece Skype for Business usuários com a capacidade de pesquisar e adicionar Skype usuários. Skype Conectividade é um recurso de Skype for Business que permite habilitar a pesquisa de federação e diretório com Skype usuários. Depois de habilitar Skype conectividade, os usuários Skype for Business poderão pesquisar e adicionar Skype usuários.
  
## <a name="skype-directory-search"></a>Skype Pesquisa de Diretório

Skype A funcionalidade de Pesquisa de Diretório Skype for Business aos usuários com a capacidade de pesquisar Skype contatos. A funcionalidade de pesquisa permite que os usuários pesquisem usando o seguinte:
  
- **Pesquisar por nome de exibição, exemplo "Desconhecido"** - Isso pode retornar muitos resultados, portanto, você pode não encontrar o que está procurando.
    
- **Pesquisar por nome de exibição mais local, exemplo "João Doe em Barcelona"** - Isso reduzirá consideravelmente os resultados da pesquisa.
    
- **Pesquisar por email, exemplo "johndoe@outlook.com"** - Isso deve retornar um resultado na maioria dos casos; aquele que corresponde exatamente ao email especificado. Mas se o mesmo email estiver associado a mais de uma conta, vários resultados poderão ser retornados.
    
- **Pesquisar por número de telefone, exemplo "123-123-1234"** - Isso deve retornar um resultado na maioria dos casos; aquele que corresponde exatamente ao telefone especificado. Telefone número deve incluir o código do país (ou seja, 1-xxx-yyy-zzzz). Se o mesmo número de telefone estiver associado a mais de uma conta, vários resultados poderão ser retornados.
    
- **Pesquisar por Skype Nome, exemplo "JohnDoe1456"** - Se a combinação exata for encontrada, ela será retornada como o primeiro resultado. Outras possíveis combinações de "nome" podem ser retornadas.
    
    > [!NOTE]
    > Skype A Pesquisa de Diretório deve ser capaz de se comunicar com os seguintes endereços IP na porta 443: 104.40.75.246, 23.101.135.34 e 40.113.86.19. 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Matriz de implantação suportada para Skype Pesquisa de Diretório

A tabela a seguir descreve o suporte para Skype Pesquisa de Diretório.
  

|&nbsp;|Skype for Business Server Front-End|Front-End do Lync Server 2013 (ou mais antigo)|Comentários|
|:-----|:-----|:-----|:-----|
|Skype for Business Server Borda   |Com suporte   |Não Suportado   |Skype for Business Server e Borda são pré-requisitos para Skype Pesquisa de Diretório   |
|Skype for Business Server Borda + Lync Server 2013 Borda implantada lado a lado   |Com suporte   |Não Suportado   |Skype O tráfego de Pesquisa de Diretório flui Skype for Business Server de Borda. O tráfego de federação passa pela borda configurada pelo administrador. Por exemplo, o administrador poderia optar por continuar a enviar tráfego de federação por meio de servidores de Borda do Lync Server 2013 que não suportam Skype Pesquisa de Diretório.   |
|Borda do Lync Server 2013 (ou mais antigo)   |Não Suportado   |Não Suportado   ||
   
> [!NOTE]
> O serviço de addressbook em execução Skype for Business Server Front End localiza a Borda pela existência da porta de pesquisa 4443 Skype no servidor de Borda. 
  
> [!NOTE]
> No caso de um cliente ter vários sites em sua implantação local e se tiver implantado apenas um servidor/pool de borda Skype for Business Server, o tráfego de pesquisa de todos os sites passará pelo servidor de Borda disponível único. O administrador precisa garantir que os pools de todos os sites possam acessar o servidor/pool Skype for Business Server Edge implantado. 
  
> [!NOTE]
> Skype o serviço gráfico irá acelerar as solicitações de pesquisa de qualquer cliente local ou Microsoft 365 ou Office 365 se a taxa de solicitação exceder 15 solicitações/segundo. 
  
> [!NOTE]
> Para clientes locais de grandes empresas, os domínios precisarão ser adicionados a uma lista de Skype de pesquisa para permitir taxas de solicitação maiores.
  
> [!NOTE]
> Skype for Business Server as solicitações de entrada serão aceleradas, se houver muitas solicitações pendentes na fila. 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online"></a>Implantando Skype conectividade para Skype for Business Online

Skype A conectividade também é um recurso do Skype for Business Online, que faz parte do Microsoft 365 e Office 365. Você pode habilitar o recurso Skype conectividade do Centro de Administração Skype for Business no Centro de administração do Microsoft 365.
  
Para Microsoft 365 Midsize Business, Office 365 Enterprise, Microsoft 365 Education e Office 365 para Governo: entre no Centro de administração do Microsoft 365 e navegue até o Skype for Business Centro de Administração. Vá para Comunicações Externas. Em Provedores de Serviços de IM Pública, clique em Habilitar. Se você quiser controlar o acesso de usuários individuais Skype Conectividade, você pode fazer isso editando as configurações de Comunicações Externas de usuários individuais.
  
Para Office 365 Small Business Premium: entre no Office 365 e vá para o Serviço de Administração Configurações mensagens \> \> instantâneas, reuniões e conferências. Ativar comunicações externas. A opção Comunicações externas a Skype conectividade e comunicações com outras organizações que usam Skype for Business.
  
Para obter mais informações sobre Skype for Business online, consulte:
  
- [Permitir que os usuários entrem em contato com usuários externos do Skype for Business](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [O que tentar se você não puder IM Skype for Business ou Skype contatos externos](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [Adicionar um contato no Skype for Business](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [Administradores: Configure Skype for Business configurações para usuários individuais](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>Implantando Skype conectividade para Skype for Business Server

Skype for Business Server usa a arquitetura de acesso de federação para dar suporte à conectividade com Skype. Essa conectividade permite que seus Skype for Business Server usuários adicionem Skype. Skype clientes também podem adicionar Skype for Business usuários à lista de contatos. Com base nas políticas definidas administrativamente Skype for Business Server os usuários poderão se comunicar usando mensagens instantâneas, ver a presença uns dos outros e iniciar chamadas de áudio e vídeo. Skype conectividade também é um recurso do Skype for Business Online e pode ser habilitado para clientes do Skype for Business Online a partir do Centro de Administração do Skype for Business no Centro de administração do Microsoft 365.
  
> [!NOTE]
> Se Skype for Business Server já estiver configurado para se conectar ao Windows Messenger usando a Pic (Conectividade pública de Mensagens Instantâneas), sua implantação já está configurada para Skype conectividade. A única alteração que você pode considerar é renomear sua entrada pic do Messenger existente como Skype. 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>O Skype for Business Server de provisionamento de conectividade de IM pública não está mais disponível

O site usado anteriormente para provisionar manualmente a federação entre implantações Skype for Business local e Skype não é mais necessário e será desligado em 15/08/2019. A federação Skype agora utiliza a descoberta de parceiros federados, que é o mesmo mecanismo necessário para federação com Skype for Business Online.

A comunicação entre qualquer implantação Skype for Business local e Skype usuários por meio da infraestrutura de IM Pública existente agora exige que a configuração do Servidor de Borda local seja compatível com o Skype for Business Online.

> [!NOTE]
> Nenhuma ação é necessária pela maioria dos clientes, incluindo todas as implantações federadas com Skype for Business Online.
  
As implantações locais são necessárias para publicar um registro SRV DNS de Federação para cada domínio que eles hospedam. As diretrizes estão disponíveis no [planejamento dns.](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning) Cada domínio deve ser resolvido pela consulta DNS SRV para um FQDN de servidor de borda que satisfaça uma match de sufixo de nível superior do domínio. Por exemplo, considere o domínio "contoso.com":

|**FQDNs válidos**|**Comment**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |Em cada caso, o FQDN exato deve estar presente no SN ou na SAN do certificado externo instalado no servidor de borda.   |
|access.contoso.com   ||
|**FQDNs inválidos**|**Motivo**|
|sip.contoso-edge.com   |Não é uma combinação de sufixo.  |
|sip.it.contoso.com   |Não é uma combinação de sufixo de nível superior.   |

Outras orientações sobre Certificados Externos podem ser encontradas em [Planejamento de certificados.](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning)

#### <a name="faqs"></a>Perguntas Frequentes

**Por que o site de provisionamento está sendo desligado?**
O mecanismo de provisionamento de IM pública (PIC) (pic.lync.com) implantado em 2006 não é mais serviceable e será desligado em 15/08/2019. Em vez disso, a federação de IM pública assumirá o mesmo modelo de federação usado pelo Skype for Business Online, conhecido como "descoberta de parceiros", em que uma implantação local é descoberta publicamente por seus registros DNS SRV de federação.

**Essa alteração significa que a federação de IM pública está sendo preterida?**
Não. A federação de IM pública continuará a ser suportada por muitos anos, provavelmente até que o produto local Skype for Business o produto local atinja o fim da vida útil.

**Nossa empresa tem uma relação híbrida (espaço de endereço compartilhado) com Skype for Business Online, somos afetados?**
Não, já que você já está federando com o Skype for Business Online, essa alteração não afetará você.
 
**Essa alteração significa que nossa empresa precisa habilitar a federação com Skype for Business Online?**
Não. Se as configurações de proxy do servidor de borda não habilitar a federação com o provedor de hospedagem do Skype for Business Online (sipfed.online.lync.com), essa alteração não afetará isso. No entanto, os mesmos requisitos de DNS e certificado que se aplicam à federação com o Skype for Business Online agora também se aplicam à federação com Skype usuários.
 
**Nossa empresa é grande e não pode alterar sua configuração de borda devido a motivos regulatórios/conformidade/etc... O que podemos fazer?**
Qualquer organização local que não possa alterar sua configuração de servidor de borda conforme especificado deve chegar ao suporte ao produto na primeira oportunidade.

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>Habilitando a Federação e a Conectividade de IM Pública (PIC)

Agora, concentre-se no Skype for Business Server ambiente e nas tarefas administrativas necessárias para configurar Skype Conectividade. Nesta seção, presumimos que o administrador tenha implantado Skype for Business Server acesso externo e configurado, também conhecido como servidores de Borda. 
  
Há três etapas principais necessárias para habilitar federação e PIC. São eles:
  
1. Configurar Federação e PIC
    
2. Configurar pelo menos uma política para dar suporte ao acesso de usuário federado
    
3. Configurar a configuração Skype de provedor PIC
    
#### <a name="1-configure-federation-and-pic"></a>1. Configurar Federação e PIC

A federação é necessária para permitir que Skype usuários se comuniquem com Skype for Business usuários em sua organização. A PIC (Conectividade de Mensagens Instantâneas Públicas) é uma classe de federação e deve ser configurada para permitir que seus usuários Skype for Business se comuniquem com Skype usuários. Federação e PIC são configurados usando o painel de Skype for Business Server de controle.
  
> [!NOTE]
> A federação PIC não é mais suportada por versões de produto anteriores ao Lync Server 2010 (Live Communication Server, Office Communications Server). As plataformas com suporte para federação PIC incluem Skype for Business Server, Lync Server 2013 e Lync Server 2010. 
  
A federação é necessária para permitir que Skype usuários se comuniquem com Skype for Business usuários em sua organização. A Pic (Conectividade de Mensagens Instantâneas Públicas) é uma classe de federação e deve ser configurada para permitir que seus usuários Skype for Business Server se comuniquem com Skype usuários. Federação e PIC são configurados usando a caixa de diálogo Configuração de Borda do Painel de Controle Skype for Business Server como mostrado na figura.
  
![Definir Novo Pool de Borda.](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> Os atributos EnableSkypeIdRouting e EnableSkypeDirectorySearch precisam ser definidos como true nas configurações de provedor público (consulte instruções posteriores) para que a Pesquisa funcione. 
  
Isso conclui as tarefas administrativas que devem ser executadas no servidor. Agora você está configurada para Skype Conectividade.
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. Configure pelo menos uma política para dar suporte ao acesso de usuário federado

Usando o Skype for Business Server de controle, um administrador deve configurar uma ou mais políticas de acesso de usuário externos para controlar se Skype usuários podem colaborar com usuários internos Skype for Business Server usuários.
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. Configure a configuração do Skype PIC

Usando o Shell de Gerenciamento Skype for Business Server, um administrador deve configurar a política de cliente Skype for Business para exibir Skype como um provedor PIC adicional. 
  
> [!NOTE]
> Os usuários dos provedores de serviço PIC (Conectividade de Mensagens Instantâneas Públicas) não poderão participar de mensagens instantâneas ou conferências em sua organização até que você também configure pelo menos uma política (etapa 2, anteriormente neste procedimento) para dar suporte à conectividade de mensagens instantâneas públicas. 
  
Para novas instalações, você pode configurar Skype Conectividade habilitando um provedor público Skype usando o Painel de Controle Skype for Business Server como mostrado na figura.
  
![Provedores Federados SIP.](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> Para configurar Skype Conectividade ao atualizar para Skype for Business Server você deve remover e adicionar o provedor Skype público existente. 
  
A configuração Skype conectividade também pode ser feita usando apenas o PowerShell. Para configurar Skype conectividade usando o PowerShell:
  
1. Em um Skype for Business Server de front-end, abra o Shell Skype for Business Server Gerenciamento.
    
2. Execute os dois comandos a seguir:
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > Se você ainda não tiver um provedor PIC em seu ambiente e estiver criando um novo provedor PIC, não precisará executar o cmdlet Remove-CsPublicProvider. 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    O que os parâmetros menos óbvios fazem?
    
   - ProxyFqdn: local de Skype de federação (propriedade/manutenção da Microsoft)
    
   - IconURL: ícone usado pelo cliente Skype for Business Lync para &amp; identificar visualmente Skype contatos
    
   - NameDecorationRoutingDomain e NameDecorationExcludedDomainList: a configuração permite que os usuários insiram as MSAs dos usuários Skype sem precisar saber sobre "decorando" domínios que não sejam da Microsoft com "msn.com". Isso elimina a necessidade de digitar "user(contoso.com)@msn.com" para todos os domínios que NÃO estão no ExcludedDomainList. O cliente SfB formatará automaticamente o MSA se o domínio NÃO estiver na lista Excluído. Adicionamos os domínios mais comuns da Conta da Microsoft à lista excluída.
    
     > [!NOTE]
     > O Provedor Público deve ser removido e adicionado novo se as alterações são feitas. Nenhuma alteração no local é permitida. 
  
     > [!NOTE]
     > Adicionado no cliente de área de trabalho do Lync Server 2013 CU5 &amp; Lync no Office 2013 SP1, o NameDecorationRoutingDomain e NameDecorationExcludedDomainList melhoram a situação em que os usuários do Lync adicionando contatos do Skype necessários para "enfeitar" domínios não-Microsoft para identificá-los e encaminhá-los para Skype (o formato de: user(contoso.com)@msn.com). Essas novas configurações permitirão a formatação automática da entrada do usuário de endereço na caixa de diálogo "Adicionar contato Skype" com a caixa de diálogo NameDecorationRoutingDomain (que deve ser definida como msn.com) se ele não contiver os domínios na NameDecorationExcludedDomainList (atualmente podemos dar suporte a msn.com, live.com, Hotmail.com, outlook.com). 
  
3. A partir de Skype for Business clientes agora podem pesquisar e adicionar um Skype usuário.
    
## <a name="clients-and-interoperability-matrix"></a>Clientes e Matriz de Interoperabilidade

A tabela a seguir descreve o status de interop entre a versão mais recente do consumidor Skype e a versão mais recente do Skype for Business.
  

|Skype Clientes|Adicionar contatos, mensagens de IM, presença, áudio e chamada de vídeo|Comment|
|:-----|:-----|:-----|
|Skype Windows Desktop   |7,6 ou superior, Windows XP e superior   |**NOVO**: o suporte adicionado Windows Skype cliente em execução no Windows XP e Windows Vista (requer a versão **7.26 ou** superior do cliente mais recente)  |
|Skype Mobile - Android Telefone e Tablet   |6.19 ou superior, executando o sistema operacional Android versão 4.0.3 ou superior   |Dispositivos de especificação baixa podem não suportar a chamada de vídeo   |
|Skype Mobile - iOS   |6,11 ou superior, no IOS 7 ou superior   |Não há suporte para iPhone 4 e anteriores, iPod 4ª geração e anterior, iPad 1ª geração   |
|Skype Mac   |7,19 ou superior, no Mac OS X 10.9 (Mavericks) ou superior   |Requer Mac OSX 10.9 ou superior   |
|Skype Universal Windows App (Windows 10) Desktop e Mobile   |Windows 10 (atualização do Redstone 1 ou posterior)   |Windows Aplicativo Universal receberá atualização no Fall 2016 adicionando suporte de interop   |
   
A tabela a seguir descreve o status de interop entre a versão mais recente do Skype for Business e a versão mais recente do Skype consumidor. 
  
|Client|Skype Pesquisa de Diretório e Adicionar Contatos|Skype A/V, interop de IM|
|:-----|:-----|:-----|
|Skype for Business   |Sim   |Sim   |
|Skype for Business no Mac   |Pode adicionar (sem pesquisa)   |Sim   |
|Lync Desktop 2013   |Pode adicionar (sem pesquisa)   |Sim   |
|Lync Web App - online e local   |N/D   |N/D   |
|Lync Mobile - Windows Phone   |Em breve   |Sim   |
|Lync Mobile - Android   |Em breve   |Sim   |
|Lync Mobile - iOS   |Em breve   |Sim   |
|Sistema de salas do Lync   |Em breve   |Sim   |
|Lync Modern App (Win 8.1)   |Sim   |Sim   |
|Lync Mac 2011   |Pode adicionar (sem pesquisa)   |Sim   |
|Lync Desktop 2010   |Pode adicionar (sem pesquisa)   |Sim   |
|Lync Phone Edition   |N/D   |N/D   |
|Lync Attendant   |N/D   |N/D   |
   
