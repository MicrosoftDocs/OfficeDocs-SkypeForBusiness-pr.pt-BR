---
title: Configurar Controlador de Borda de Sessão - Vários locatários
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Saiba como configurar um Controlador de Borda de Sessão (SBC) para atender a vários locatários para parceiros da Microsoft e/ou operadoras PSTN.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b81709b46774762036ba9465444d066a0adf019c
ms.sourcegitcommit: ac73536f790f83a61eeb2eb8c6b71662f7bd26fc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50110234"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>Configurar um controlador de borda da sessão para vários locatários

O Roteamento Direto dá suporte à configuração de um SBC (Controlador de Borda de Sessão) para atender a vários locatários.

> [!NOTE]
> Este cenário foi projetado para parceiros da Microsoft e/ou operadoras PSTN, chamados de operadoras posteriormente neste documento. Uma operadora vende serviços de telefonia entregues ao Microsoft Teams para seus clientes. 

Uma operadora:
- Implanta e gerencia um SBC em seu datacenter (os clientes não precisam implementar um SBC e recebem serviços de telefonia da operadora no cliente do Teams).
- Interconecta o SBC a vários locatários.
- Fornece serviços PSTN aos clientes.
- Gerencia a qualidade de chamada de ponta a ponta.
- Encargos separadamente para serviços PSTN.

A Microsoft não gerencia operadoras. A Microsoft oferece um PBX (Microsoft Phone System) e um cliente do Teams. A Microsoft também certifica telefones e certifica SBCs que podem ser usados com o Microsoft Phone System. Antes de escolher uma operadora, certifique-se de que sua escolha tenha um SBC certificado e possa gerenciar a qualidade da voz de ponta a ponta.

A seguir estão as etapas técnicas de implementação para configurar o cenário.

**Somente transportadora:**
1. Implante o SBC e configure-o para o cenário de hospedagem de acordo com as [instruções dos fornecedores SBC certificados.](#deploy-and-configure-the-sbc)
2. Registre um nome de domínio base no locatário da operadora e solicite um certificado curinga.
3. Registre um subdomínio para cada cliente, que faz parte do domínio base.

**Operadora com um Administrador Global do Cliente:**
1. Adicione o nome do subdomínio ao locatário do cliente.
2. Ativar o nome do subdomínio.
3. Configure o tronco da operadora para o locatário do cliente e provisione usuários.

*Verifique se você entende as noções básicas de DNS e como o nome de domínio é gerenciado no Microsoft 365 ou no Office 365. Revise [Obter ajuda com domínios do Microsoft 365 ou do Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) antes de prosseguir.*

## <a name="deploy-and-configure-the-sbc"></a>Implantar e configurar o SBC

Para ver as etapas detalhadas sobre como implantar e configurar SBCs para um cenário de hospedagem de SBC, consulte a documentação do fornecedor SBC.

- **AudioCodes:** [Anotações](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)de Configuração de Roteamento Direto, a configuração do cenário de hospedagem SBC descrito em "Conectando AudioCodes SBC à Nota de Configuração do Modelo de Hospedagem de Roteamento Direto do Microsoft Teams". 
- **Oracle: Anotações** [de Configuração](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html)de Roteamento Direto, a configuração do cenário de hospedagem de SBC é descrita na seção "Microsoft". 
- **Comunicações da Faixa de Opções:**  Consulte o Guia de Configuração principal [do Microsoft Teams](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) do Microsoft Teams da Faixa de Opções para ver a documentação sobre como configurar SBCs da Série Core da Faixa de Opções e para esta página Prática prática da Faixa de Opções – Configurando operadoras para a borda [SBC](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier) de Roteamento Direto do Microsoft Teams
- **Te-Systems (anynode):**  Registre-se na página [da Comunidade de SISTEMAS TE](https://community.te-systems.de/) para ver a documentação e exemplos sobre como configurar qualquer SBC denodo para vários locatários.
- **Metaswear:**  Registre-se na [página da Comunidade Metaswstat](https://manuals.metaswitch.com/MAN39555) para ver a documentação sobre como habilitar o SBC de Metameta para vários locatários.

> [!NOTE]
> Preste atenção em como configurar o header "Contato". O header de Contato é usado para encontrar o locatário do cliente na mensagem de convite de entrada. 

## <a name="register-a-base-domain-and-subdomains"></a>Registrar um domínio base e subdomas

Para o cenário de hospedagem, você precisa criar:
- Um nome de domínio base pertencente à operadora.
- Um subdomínio que faz parte do nome de domínio base em todos os locatários de clientes.

No exemplo a seguir:
- A Adatum é uma operadora que atende vários clientes fornecendo serviços de Internet e telefonia.
- O Woodgrove Bank, a Contoso e a Adventure Works são três clientes que têm domínios do Microsoft 365 ou do Office 365, mas recebem os serviços de telefonia do Adatum.

Os subdomas DEVEM corresponder ao nome FQDN do tronco que será configurado para o cliente e o FQDN no header de Contato ao enviar o Convite para o Microsoft 365 ou o Office 365.  

Quando uma chamada chega na interface de Roteamento Direto do Microsoft 365 ou office 365, a interface usa o header contato para encontrar o locatário onde o usuário deve ser procurado. O Roteamento Direto não usa a olhada de número de telefone no Convite, pois alguns clientes podem ter números não DID que podem se sobrepor a vários locatários. Portanto, o nome FQDN no header de Contato é necessário para identificar o locatário exato para procurar o usuário pelo número de telefone.

*Consulte  [Obter ajuda com domínios do Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) para obter mais informações sobre como criar nomes de domínio em organizações do Microsoft 365 ou office 365.*

O diagrama a seguir resume os requisitos para basear domínio, subdomains e header de Contato.

![Diagrama mostrando os requisitos para domínios e o header de contato](media/direct-routing-1-sbc-requirements.png)

O SBC requer um certificado para autenticar as conexões. Para o cenário de hospedagem de SBC, a operadora precisa solicitar um certificado com CN e/ou SAN *\* .base_domain (por exemplo, \* .customers.adatum.biz).* Esse certificado pode ser usado para autenticar conexões com vários locatários atendidos de um único SBC.


A tabela a seguir é um exemplo de uma configuração.


|Novo nome de domínio |Tipo|Registrado  |Certificado CN/SAN para SBC  |Domínio padrão do locatário no exemplo  |Nome FQDN que o SBC deve apresentar no header contato ao enviar chamadas para os usuários|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    Base     |     No locatário da operadora  |    \*.customers.adatum.biz  |   adatum.biz      |NÃO, este é um locatário de serviço, nenhum usuário |
|sbc1.customers.adatum.biz|    Subdomínio  |    Em um locatário do cliente  |    \*.customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   Subdomínio | Em um locatário do cliente   |   \*.customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   Subdomínio | Em um locatário do cliente |   \*.customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |
||         |         |         |         |         |

Para configurar a base e os subdomas, siga as etapas descritas abaixo. No exemplo, configuraremos um nome de domínio base (customers.adatum.biz) e um subdomínio para um cliente (sbc1.customers.adatum.biz no locatário do Woodgrove Bank).

> [!NOTE]
> Use sbcX.customers.adatum.biz para habilitar a voz no locatário da operadora. sbcX pode ser qualquer nome de host alfanumérico exclusivo e válido.

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>Registrar um nome de domínio base no locatário da operadora

**Essas ações são executadas no locatário da operadora.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>Certifique-se de que você tenha os direitos apropriados no locatário da operadora

Você só poderá adicionar novos domínios se entrar no Centro de administração do Microsoft 365 como Administrador Global. 

Para validar a função que você tem, entre no Centro de administração do Microsoft 365 ( , vá para Usuários Ativos usuários e verifique se você tem uma função de Administrador https://portal.office.com)   >  Global. 

Para obter mais informações sobre funções de administrador e como atribuir uma função no Microsoft 365 ou no Office 365, consulte [Sobre as funções de administrador.](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>Adicionar um domínio base ao locatário e confirmá-lo

1. No Centro de administração do Microsoft 365, vá para **Configurar**  >  **Domínios**  >  **Adicionar domínio.**
2. Na caixa **Inserir um domínio que você possui,** digite o FQDN do domínio base. No exemplo a seguir, o domínio base é *customers.adatum.biz.*

    ![Captura de tela mostrando a página Adicionar um domínio](media/direct-routing-2-sbc-add-domain.png)

3. Click **Next**.
4. No exemplo, o locatário já adatum.biz como um nome de domínio verificado. O assistente não solicitará verificação adicional porque customers.adatum.biz é um subdomínio para o nome já registrado. No entanto, se você adicionar um FQDN que não tenha sido verificado antes, será necessário passar pelo processo de verificação. O processo de verificação é [descrito abaixo.](#add-a-subdomain-to-the-customer-tenant-and-verify-it)

    ![Captura de tela mostrando a confirmação de um nome de domínio verificado](media/direct-routing-3-sbc-verify-domain.png)

5. Clique **em** Próximo e, na página Atualizar Configurações **de DNS,** selecione Eu mesmo adicionarei os registros **DNS** e clicarei **em Próximo.**
6. Na página seguinte, limpe todos os valores (a menos que você queira usar o nome de domínio para Exchange, SharePoint ou Teams/Skype for Business), clique em Próximo e, em seguida, clique em **Concluir.** Certifique-se de que seu novo domínio está no status de configuração concluído.

    ![Captura de tela mostrando domínios com o status de Configuração concluído](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a>Ativar o nome de domínio

Depois de registrar um nome de domínio, você precisa ativá-lo adicionando pelo menos um usuário com licença do Sistema telefônico e atribuindo um endereço SIP com a parte FQDN do endereço SIP que corresponde ao domínio base criado. A licença pode ser revogada após a ativação do domínio (pode levar até 24 horas).

> [!NOTE]
> O locatário da operadora deve manter pelo menos uma licença do Sistema telefônico atribuída ao locatário para evitar a remoção da configuração do Skype for Business. 

*Consulte [Obter ajuda com domínios do Microsoft 365 ou do Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) para obter mais informações sobre como adicionar usuários em organizações do Microsoft 365 ou do Office 365.*

Por exemplo: test@customers.adatum.biz

![Captura de tela da página de ativação de domínio base](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>Registrar um nome de subdomínio em um locatário de cliente

Você precisará criar um nome de subdomínio exclusivo para cada cliente. Neste exemplo, criaremos um subdomínio sbc1.customers.adatum.biz em um locatário com o nome de domínio padrão woodgrovebank.us.

**Todas as ações abaixo estão no locatário do cliente.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>Verifique se você tem direitos apropriados no locatário do cliente

Você só poderá adicionar novos domínios se entrar no Centro de administração do Microsoft 365 como Administrador Global. 

Para validar a função que você tem, entre no Centro de administração do Microsoft 365 ( , vá para Usuários Ativos usuários e verifique se você tem uma função de Administrador https://portal.office.com)   >  Global. 

Para obter mais informações sobre funções de administrador e como atribuir uma função no Microsoft 365 ou no Office 365, consulte [Sobre as funções de administrador.](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>Adicionar um subdomínio ao locatário do cliente e confirmá-lo
1. No Centro de administração do Microsoft 365, vá para **Configurar**  >  **Domínios**  >  **Adicionar domínio.**
2. Na caixa **Inserir um domínio que você possui,** digite o FQDN do subdomínio para este locatário. No exemplo abaixo, o subdomínio é sbc1.customers.adatum.biz.

    ![Captura de tela da página Adicionar um domínio](media/direct-routing-5-sbc-add-customer-domain.png)

3. Click **Next**.
4. O FQDN nunca foi registrado no locatário. Na próxima etapa, você precisará verificar o domínio. Selecione **Adicionar um registro TXT.** 

    ![Captura de tela da página Verificar domínio](media/direct-routing-6-sbc-verify-customer-domain.png)

5. Clique **em** Próximo e observe o valor TXT gerado para verificar o nome de domínio.

    ![Captura de tela dos registros de texto na página Verificar domínio](media/direct-routing-7-sbc-verify-domain-txt.png)

6. Crie o registro TXT com o valor da etapa anterior no provedor de hospedagem de DNS da operadora.

    ![Captura de tela mostrando a criação do registro TXT](media/direct-routing-8-sbc-txt-record.png)

    Para obter mais informações, consulte [Criar registros DNS em qualquer provedor de hospedagem de DNS.](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)

7. Volte para o Centro de administração do Microsoft 365 do cliente e clique em **Verificar.** 
8. Na próxima página, selecione **Eu mesmo adicionarei** os registros DNS e clicarei em **Próximo.**

    ![Captura de tela das opções na página Atualizar configurações de DNS](media/direct-routing-9-sbc-update-dns.png)

9. Na página **Escolher seus serviços online,** limpe todas as opções e clique em **Próxima.**

    ![Captura de tela da página Escolher seus serviços online](media/direct-routing-10-sbc-choose-services.png)

10. Clique **em Concluir** na página atualizar **configurações de DNS.**

    ![Captura de tela da página Atualizar configurações de DNS](media/direct-routing-11-sbc-update-dns-finish.png)

11. Verifique se o status está **Configuração concluído.** 
    
    ![Captura de tela da página mostrando o status da Configuração concluída](media/direct-routing-12-sbc-setup-complete.png)
    
> [!NOTE]
> A URL base e o subdomínio do cliente individual devem estar no mesmo locatário para permitir que você adicione um tronco _de rota_ direta.

### <a name="activate-the-subdomain-name"></a>Ativar o nome do subdomínio

Depois de registrar um nome de domínio, você precisa ativá-lo adicionando pelo menos um usuário e atribuindo um endereço SIP com a parte FQDN do endereço SIP que corresponde ao subdomínio criado no locatário do cliente. A licença pode ser revogada do usuário após a ativação do subdomínio (pode levar até 24 horas).

*Consulte [Obter ajuda com domínios do Microsoft 365 ou do Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) para obter mais informações sobre como adicionar usuários em organizações do Microsoft 365 ou do Office 365.*

Por exemplo: test@sbc1.customers.adatum.biz

![Captura de tela da Ativação da página de subdomínio](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>Criar um tronco e provisioná-la para usuários

Com a versão inicial do Roteamento Direto, a Microsoft exigia que um tronco fosse adicionado a cada locatário atendido (locatário do cliente) usando o New-CSOnlinePSTNGateway.

No entanto, isso não se mostrou ideal por dois motivos:
 
- **Gerenciamento de sobrecarga.** A desativação ou o esvaziamento de um SBC, por exemplo, altera alguns parâmetros, como habilenciar ou desabilitar o bypass de mídia. Alterar a porta requer a alteração de parâmetros em vários locatários (executando Set-CSOnlinePSTNGateway), mas na verdade é o mesmo SBC. 

-  **Processamento de sobrecarga.** Coleta e monitoramento de dados de integridade do tronco - as opções SIP coletadas de vários troncos lógicos que são, na verdade, o mesmo SBC e o mesmo tronco físico, atrasam o processamento dos dados de roteamento.
 
Com base nesse comentário, a Microsoft apresenta uma nova lógica para provisionar os troncos para os locatários de clientes.

Duas novas entidades foram introduzidas:
-    Um tronco de operadora registrado no locatário da operadora usando o comando New-CSOnlinePSTNGateway, por exemplo, New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true.

-    Um tronco derivado, que não requer registro. É simplesmente um nome de host desejado adicionado do tronco da transportadora. Ela deriva todos os parâmetros de configuração do tronco da operadora. O tronco derivado não precisa ser criado no PowerShell, e a associação com o tronco da transportadora se baseia no nome do FQDN (veja detalhes abaixo).

**Lógica de provisionamento e exemplo**

-    As operadoras só precisam configurar e gerenciar um único tronco (tronco de transportadora no domínio da operadora), usando o comando Set-CSOnlinePSTNGateway transporte. No exemplo acima, é adatum.biz;
-    No locatário do cliente, a operadora só precisa adicionar o FQDN do tronco derivado às políticas de roteamento de voz dos usuários. Não é necessário executar uma New-CSOnlinePSTNGateway para um tronco.
-    O tronco derivado, como o nome sugere, herda ou deriva todos os parâmetros de configuração do tronco da operadora. Exemplos:
-    Customers.adatum.biz – o tronco da operadora que precisa ser criado no locatário da operadora.
-    Sbc1.customers.adatum.biz – o tronco derivado em um locatário de cliente que não precisa ser criado no PowerShell.  Você pode simplesmente adicionar o nome do tronco derivado no locatário do cliente na política de roteamento de voz online sem criar.
-   A operadora precisará configurar o registro DNS resolvendo o FQDN de tronco derivado para o endereço IP SBC da operadora.

-    Todas as alterações feitas em um tronco de operadora (no locatário da operadora) são aplicadas automaticamente aos troncos derivados. Por exemplo, as transportadoras podem alterar uma porta SIP no tronco da transportadora, e essa alteração se aplica a todos os troncos derivados. A nova lógica para configurar os troncos simplifica o gerenciamento, pois você não precisa ir para todos os locatários e alterar o parâmetro em cada tronco.
-    As opções são enviadas somente para o FQDN do tronco da operadora. O status de saúde do tronco da transportadora é aplicado a todos os troncos derivados e é usado para decisões de roteamento. Saiba mais sobre as [opções de Roteamento Direto.](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot)
-    A transportadora pode esvaziar o tronco da transportadora, e todos os troncos derivados também serão esvaziados. 
 

**Migração do modelo anterior para o tronco da operadora**
 
Para migrar da implementação atual do modelo hospedado da operadora para o novo modelo, as operadoras precisarão reconfigurar os troncos para locatários de clientes. Remover os troncos dos locatários de clientes usando Remove-CSOnlinePSTNGateway (deixando o tronco no locatário da operadora)-

É altamente recomendável migrar para a nova solução assim que possível, pois aprimoraremos o monitoramento e o provisionamento usando a operadora e o modelo de tronco derivado.
 

Consulte as instruções do fornecedor [SBC](#deploy-and-configure-the-sbc) sobre como configurar o envio do nome FQDN de subdomains no header contato.

## <a name="considerations-for-setting-up-muti-tenant-failover"></a>Considerações sobre como configurar o failover muti-tenant 

Para configurar o failover para um ambiente de vários locatários, você precisará fazer o seguinte:

- Para cada locatário, adicione os FQDNs para dois SBCs diferentes.  Por exemplo:

   customer1.sbc1.contoso.com <br>
   customer1.sbc2.contoso.com <br>

- Nas políticas de Roteamento de Voz Online dos usuários, especifique ambos os SBCs.  Se um SBC falhar, a política de roteamento encaminhará chamadas para o segundo SBC.


## <a name="see-also"></a>Confira também

[Planejar o Roteamento Direto](direct-routing-plan.md)

[Configurar o Roteamento Direto](direct-routing-configure.md)
