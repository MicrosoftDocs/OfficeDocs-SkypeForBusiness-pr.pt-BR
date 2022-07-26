---
title: Configurar o Controlador de Borda de Sessão – Vários locatários
ms.reviewer: filippse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Saiba como configurar um Controlador de Borda de Sessão (SBC) para atender a vários locatários para parceiros da Microsoft e/ou operadoras PSTN.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8880f912ae21af3bf269e86469241f345bc33f74
ms.sourcegitcommit: f5d784df59a8010b390691bbb20c4ea66c46280b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/26/2022
ms.locfileid: "67005351"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>Configurar um controlador de borda da sessão para vários locatários

O Roteamento Direto dá suporte à configuração de um controlador de borda de sessão (SBC) para atender a vários locatários.

> [!NOTE]
> Esse cenário foi projetado para parceiros da Microsoft e/ou operadoras PSTN, chamados de operadoras posteriormente neste documento. Uma operadora vende serviços de telefonia entregues ao Microsoft Teams para seus clientes. 

Uma operadora:
- Implanta e gerencia um SBC em seu datacenter (os clientes não precisam implementar um SBC e recebem serviços de telefonia da operadora no cliente do Teams).
- Interconecta o SBC a vários locatários.
- Fornece serviços PSTN (Rede Telefônica Pública Comunada) aos clientes.
- Gerencia a qualidade da chamada de ponta a ponta.
- Encargos separadamente para serviços PSTN.

A Microsoft não gerencia operadoras. A Microsoft oferece o Sistema de Telefonia , um PBX (Private Branch Exchange) e um cliente do Teams. A Microsoft também certifica telefones e certifica os SBCs que podem ser usados com o Sistema de Telefonia. Antes de escolher uma operadora, verifique se sua escolha tem um SBC certificado e pode gerenciar a qualidade da voz de ponta a ponta.

A seguir estão as etapas de implementação técnica para configurar o cenário.

**Somente operadora:**
1. Implante o SBC e configure-o para o cenário de hospedagem de acordo com as [instruções dos fornecedores SBC certificados](#deploy-and-configure-the-sbc).
2. Registre um nome de domínio base no locatário da operadora e solicite um certificado curinga.
3. Registre um subdomínio para cada cliente, que faz parte do domínio base.

**Operadora com um Administrador Global do Cliente:**
1. Adicione o nome do subdomínio ao locatário do cliente.
2. Ative o nome do subdomínio.
3. Configure o tronco da operadora para o locatário do cliente e provisione usuários.

*Certifique-se de entender as noções básicas de DNS e como o nome de domínio é gerenciado no Microsoft 365. Consulte [Obter ajuda com domínios do Microsoft 365](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) antes de continuar.*

## <a name="deploy-and-configure-the-sbc"></a>Implantar e configurar o SBC

Para obter etapas detalhadas sobre como implantar e configurar SBCs para um cenário de hospedagem SBC, consulte a documentação do fornecedor SBC.

- **Audiocodes:** Consulte [as notas de Configuração](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams) de Roteamento Direto para configuração do cenário de hospedagem SBC, conforme descrito em "Conectando AudioCodes SBC à Nota de Configuração do Modelo de Hospedagem de Roteamento Direto do Microsoft Teams". 
- **Oracle:** Consulte [as notas de Configuração de](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html) Roteamento Direto para configuração do cenário de hospedagem SBC, conforme descrito na seção "Microsoft". 
- **Comunicações da Faixa de Opções:** Consulte [o Guia de Configuração do Microsoft Teams do SBC Core](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+MS+Teams+Solution+Guide) de Comunicações da Faixa de Opções para obter documentação sobre como configurar SBCs da Série Core da Faixa de Opções. Confira também a [Melhor Prática da Faixa de Opções – Configurando operadoras para o SBC Edge de Roteamento Direto do Microsoft Teams](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)
- **Te-Systems (anynode):** Registre-se no site da página da Comunidade [te-Systems](https://community.te-systems.de/) para obter documentação e exemplos sobre como configurar anynode SBC para vários locatários.
- **Metaswitch:** Registre-se [no site da página da Comunidade Metaswitch](https://manuals.metaswitch.com/MAN39555) para obter documentação sobre como habilitar o Perimeta SBC para vários locatários.

> [!NOTE]
> Verifique se você sabe como configurar o cabeçalho "Contato". O cabeçalho Contato é usado para localizar o locatário do cliente na mensagem de convite de entrada. 

## <a name="register-a-base-domain-and-subdomains"></a>Registrar um domínio base e subdomínios

Para o cenário de hospedagem, você precisa criar:

- Um nome de domínio base pertencente à operadora.
- Um subdomínio que faz parte do nome de domínio base em cada locatário do cliente.

No exemplo a seguir:

- A Adatum é uma operadora que atende a vários clientes fornecendo serviços de Internet e telefonia.
- O Woodgrove Bank, a Contoso e a Adventure Works são três clientes que têm domínios do Microsoft 365, mas recebem os serviços de telefonia do Adatum.

Os subdomínios **DEVEM** corresponder ao nome FQDN do tronco que será configurado para o cliente e o FQDN no cabeçalho Contato ao enviar o Convite para o Microsoft 365. 

Quando uma chamada chega à interface de Roteamento Direto do Microsoft 365, a interface usa o cabeçalho Contato para localizar o locatário em que o usuário deve ser pesquisado. O Roteamento Direto não usa a pesquisa de número de telefone no Convite, pois alguns clientes podem ter números não DID que podem se sobrepor a vários locatários. Portanto, o nome do FQDN no cabeçalho Contato é necessário para identificar o locatário exato para pesquisar o usuário pelo número de telefone.

*Para obter mais informações sobre como criar nomes de domínio em organizações do Microsoft 365, consulte [Obter ajuda com domínios do Microsoft 365](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).*

O diagrama a seguir resume os requisitos de domínio base, subdomínios e cabeçalho de contato.

:::image type="content" source="media/direct-routing-1-sbc-requirements.png" alt-text="Diagrama mostrando os requisitos para domínios e cabeçalho de contato." lightbox="media/direct-routing-1-sbc-requirements.png":::

O SBC requer um certificado para autenticar as conexões. Para o cenário de hospedagem SBC, a operadora precisa solicitar um certificado com CN e/ou SAN *\*.base_domain (por exemplo, \*.customers.adatum.biz)*. Esse certificado pode ser usado para autenticar conexões com vários locatários atendidos de um único SBC.

A tabela a seguir é um exemplo de uma configuração.


|Novo nome de domínio |Tipo|Registrado  |Certificado CN/SAN para SBC  |Domínio padrão do locatário no exemplo  |Nome do FQDN que o SBC deve apresentar no cabeçalho Contato ao enviar chamadas aos usuários|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    Base     |     No locatário da operadora  |    \*.customers.adatum.biz  |   adatum.biz      |NA, este é um locatário de serviço, nenhum usuário |
|sbc1.customers.adatum.biz|    Subdomínio  |    Em um locatário do cliente  |    \*.customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   Subdomínio | Em um locatário do cliente   |   \*.customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   Subdomínio | Em um locatário do cliente |   \*.customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |

Para configurar a base e os subdomínios, siga as etapas descritas abaixo. Este exemplo configura um nome de domínio base (customers.adatum.biz) e um subdomínio para um cliente (sbc1.customers.adatum.biz locatário do Woodgrove Bank).

> [!NOTE]
> Use sbcX.customers.adatum.biz para habilitar a voz no locatário da operadora; sbcX pode ser qualquer nome de host alfanumérico exclusivo e válido.

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>Registrar um nome de domínio base no locatário da operadora

**Essas ações são executadas no locatário da operadora.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>Verifique se você tem direitos apropriados no locatário da operadora

Você só poderá adicionar novos domínios se tiver entrado no Centro de administração do Microsoft 365 como administrador global. 

Para validar a função que você tem, entre no Centro de administração do Microsoft 365 (https://portal.office.com)acesse  >  Usuários Ativos dos Usuários e verifique se você tem uma função de Administrador Global. 

Para obter mais informações sobre funções de administrador e como atribuir uma função no Microsoft 365, consulte [Sobre funções de administrador](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>Adicionar um domínio base ao locatário e confirmá-lo

1. No Centro de administração do Microsoft 365, vá para **Configurar** > **Domínios** > **adicionar domínio**.

2. Na caixa **Inserir um domínio que você possui** , digite o FQDN do domínio base. No exemplo a seguir, o domínio base é *customers.adatum.biz*.

3. Click **Next**.

4. Neste exemplo, o locatário já tem adatum.biz nome de domínio verificado. O assistente não solicitará verificação adicional porque customers.adatum.biz é um subdomínio para o nome já registrado. No entanto, se você adicionar um FQDN que não foi verificado antes, precisará passar pelo processo de verificação. O processo de verificação é [descrito abaixo](#add-a-subdomain-to-the-customer-tenant-and-verify-it).

5. Selecione **Avançar** e, na página Atualizar **Configurações de DNS** , selecione **Eu mesmo** adicionarei os registros DNS e **selecionarEi Avançar**.

6. Na próxima página, desmarque todos os valores (a menos que você queira usar o nome de domínio para Exchange, SharePoint, Teams ou Skype for Business), selecione Avançar **e, em** seguida, **selecione Concluir**. Verifique se o novo domínio está no status completo da Instalação.

### <a name="activate-the-domain-name"></a>Ativar o nome de domínio

Depois de registrar um nome de domínio, você precisa ativá-lo adicionando pelo menos um usuário licenciado do Teams ou uma conta de recurso. As contas aceitáveis serão licenciadas com qualquer uma das seguintes SKUs:

- Conta de usuário com Office 365 E1/E3/E5/A3/A5 ou Microsoft 365 E3/E5/A3/A5
- Conta de usuário com Office 365 F1/F3 ou Microsoft 365 F1/F3
- Conta de Usuário com Telefone de Área Comum
- Conta de recurso com **Telefonia do Microsoft Teams conta de recurso**

Além disso, o UPN da conta (Nome UPN) ou o Skype for Business SIP local devem usar o mesmo FQDN que o domínio recém-criado.

Para obter mais informações sobre como adicionar usuários em organizações do Microsoft 365, consulte [Obter ajuda com domínios do Microsoft 365](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

Por exemplo: test@customers.adatum.biz

![Captura de tela da página de ativação de domínio base.](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>Registrar um nome de subdomínio em um locatário do cliente

Você precisará criar um nome de subdomínio exclusivo para cada cliente. Neste exemplo, criaremos um subdomínio sbc1.customers.adatum.biz em um locatário com o nome de domínio padrão woodgrovebank.us.

**Todas as ações abaixo estão no locatário do cliente.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>Verifique se você tem direitos apropriados no locatário do cliente

Você só poderá adicionar novos domínios se tiver entrado no Centro de administração do Microsoft 365 como administrador global. 

Para validar a função que você tem, entre no Centro de administração do Microsoft 365 (https://portal.office.com)acesse  >  Usuários Ativos dos Usuários e verifique se você tem uma função de Administrador Global. 

Para obter mais informações sobre funções de administrador e como atribuir uma função no Microsoft 365, consulte [Sobre funções de administrador](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>Adicione um subdomínio ao locatário do cliente e verifique-o

1. No Centro de administração do Microsoft 365, vá para **Configurar** > **Domínios** > **adicionar domínio**.

2. Na caixa **Inserir um domínio que você possui** , digite o FQDN do subdomínio para esse locatário. No exemplo abaixo, o subdomínio é sbc1.customers.adatum.biz.

3. Selecione **Avançar**.

4. O FQDN nunca foi registrado no locatário. Na próxima etapa, você precisará verificar o domínio. Selecione **Adicionar um registro TXT**. 

5. Selecione **Avançar** e observe o valor TXT gerado para verificar o nome de domínio.

    ![Captura de tela dos registros de texto na página Verificar domínio.](media/direct-routing-7-sbc-verify-domain-txt.png)

6. Crie o registro TXT com o valor da etapa anterior no provedor de hospedagem DNS da operadora.

    Para obter mais informações, consulte [Criar registros DNS em qualquer provedor de hospedagem DNS](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).

7. Vá para a conta do Centro de administração do Microsoft 365 e selecione **Verificar**. 

8. Na próxima página, selecione **Eu mesmo adicionarei os registros DNS** e selecionar **Avançar**.

9. Na página **Escolher seu serviços online**, desmarque todas as opções e selecione **Avançar**.

10. Selecione **Concluir** na página **Atualizar configurações de DNS** .

11. Verifique se o status da Instalação **foi concluído**.

    ![Captura de tela da página mostrando o status da Instalação concluída.](media/direct-routing-12-sbc-setup-complete.png)

> [!NOTE]
> A URL base e o subdomínio do cliente individual precisam estar no mesmo locatário para permitir que você adicione um tronco _de rota_ direta.

### <a name="activate-the-subdomain-name"></a>Ativar o nome do subdomínio

Depois de registrar um nome de subdomínio, você precisará ativá-lo adicionando pelo menos um usuário licenciado do Teams ou uma conta de recurso. As contas aceitáveis serão licenciadas com qualquer uma das seguintes SKUs:

-   Conta de usuário com Office 365 E1/E3/E5/A3/A5 ou Microsoft 365 E3/E5/A3/A5
-   Conta de usuário com Office 365 F1/F3 ou Microsoft 365 F1/F3
-   Conta de Usuário com Telefone de Área Comum
-   Conta de recurso com uma **licença Telefonia do Microsoft Teams conta de** recurso

Além disso, o UPN da conta (Nome UPN) ou o Skype for Business SIP local devem usar o mesmo FQDN que o subdomínio recém-criado.

Para obter mais informações sobre como adicionar usuários em organizações do Microsoft 365, consulte [Obter ajuda com o Microsoft 365](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

Por exemplo: test@sbc1.customers.adatum.biz

![Captura de tela da página Ativação do subdomínio.](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>Criar um tronco e provisionar usuários

Com a versão inicial do Roteamento Direto, a Microsoft exigia que um tronco seja adicionado a cada locatário atendido (locatário do cliente) usando o cmdlet New-CSOnlinePSTNGateway cliente.

No entanto, esse método não se mostrou ideal por dois motivos:
 
- **Gerenciamento de sobrecarga**. Descarregar ou esvaziar um SBC, por exemplo, altera alguns parâmetros, como habilitar ou desabilitar o bypass de mídia. Alterar a porta requer a alteração de parâmetros em vários locatários (executando Set-CSOnlinePSTNGateway), mas na verdade é o mesmo SBC. 

-  **Processamento de sobrecarga**. Coleta e monitoramento de dados de integridade do tronco – as opções SIP coletadas de vários troncos lógicos que são, na realidade, o mesmo SBC e o mesmo tronco físico, atrasam o processamento dos dados de roteamento.
 
Com base nos comentários, a Microsoft está trazendo uma nova lógica para provisionar os troncos para os locatários do cliente.

Duas novas entidades foram introduzidas:

- Um tronco de operadora registrado no locatário da operadora usando o comando New-CSOnlinePSTNGateway. Por exemplo: 
   
   ```PowerShell
   New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true
    ```

- Um tronco derivado que não requer registro. É simplesmente um nome de host desejado adicionado do tronco da operadora. Ela deriva todos os seus parâmetros de configuração do tronco da operadora. A associação com o tronco da transportadora baseia-se no nome do FQDN (veja os detalhes abaixo).

**Exemplo e lógica de provisionamento**

- As operadoras precisam configurar e gerenciar apenas um único tronco (o tronco da operadora no domínio da operadora) usando o comando Set-CSOnlinePSTNGateway usuário. No exemplo acima, ele é adatum.biz.

- No locatário do cliente, a operadora precisa adicionar o FQDN de tronco derivado às rotas de voz. Não há necessidade de executar New-CSOnlinePSTNGateway para um tronco.

- O tronco derivado, como o nome sugere, herda ou deriva todos os parâmetros de configuração do tronco da operadora. 

Exemplos:
- Customers.adatum.biz – o tronco da operadora que precisa ser criado no locatário da operadora.

- Sbc1.customers.adatum.biz – o tronco derivado em um locatário do cliente. Você pode adicionar o nome do tronco derivado no locatário do cliente na política de roteamento de voz online sem criá-lo.

- A operadora precisará configurar o registro DNS resolvendo o FQDN do tronco derivado para o endereço IP SBC da operadora.

- Todas as alterações feitas em um tronco de operadora (no locatário da operadora) são aplicadas automaticamente a troncos derivados. Por exemplo, as operadoras podem alterar uma porta SIP no tronco da transportadora, e essa alteração se aplica a todos os troncos derivados. A nova lógica para configurar os troncos simplifica o gerenciamento, pois você não precisa ir para todos os locatários e alterar o parâmetro em cada tronco.

- As opções são enviadas somente para o FQDN do tronco da operadora. O status de integridade do tronco da transportadora é aplicado a todos os troncos derivados e é usado para decisões de roteamento. Saiba mais sobre as [opções de Roteamento Direto](./direct-routing-monitor-and-troubleshoot.md).

- O porta-aviões pode esvaziar o porta-malas, e todos os troncos derivados também serão drenados. 
 
> [!NOTE]
> As regras de conversão de números aplicadas no tronco da transportadora não se aplicam a troncos derivados. Esse é um problema conhecido. Como uma solução alternativa, as regras de conversão de números devem ser criadas para o locatário de cada cliente.

**Migração do modelo anterior para o tronco da operadora**
 
Para a migração da implementação atual do modelo hospedado da operadora para o novo modelo, as operadoras precisarão reconfigurar os troncos para locatários do cliente. Remova os troncos dos locatários do cliente usando Remove-CSOnlinePSTNGateway (deixando o tronco no locatário da operadora)-

É altamente recomendável migrar para a nova solução assim que possível, pois aprimoraremos o monitoramento e o provisionamento usando a operadora e o modelo de tronco derivado.
 
Para obter mais informações sobre como configurar o envio do nome FQDN de subdomínios no cabeçalho Contato, consulte as instruções [do fornecedor SBC](#deploy-and-configure-the-sbc).

## <a name="considerations-for-setting-up-multi-tenant-failover"></a>Considerações para configurar o failover multilocatário 

Para configurar o failover para um ambiente multilocatário, você precisará fazer o seguinte:

- Para cada locatário, adicione os FQDNs para dois SBCs diferentes. Por exemplo:

   customer1.sbc1.contoso.com <br>
   customer1.sbc2.contoso.com <br>

- Nas Rotas de Voz Online, especifique ambos os SBCs. Se um SBC falhar, a política de roteamento roteará chamadas para o segundo SBC.


## <a name="see-also"></a>Confira também

[Planejar o Roteamento Direto](direct-routing-plan.md)

[Configurar o Roteamento Direto](direct-routing-configure.md)
