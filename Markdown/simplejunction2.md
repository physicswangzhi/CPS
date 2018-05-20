
# Simple Junction: {\it Matsubara Formalism}

First we consider tunneling current in the textbok. First, we repeat his derivation following Mahan's Book, in **page 85, page 207 and page 789**. The Hamiltonian of the junction writes as,
$$
H=H_{R}+H_L+H_T=H_0+H_T
$$

with the Hamiltonians for the left side,
$$
H_R =\sum_{\sigma,{\bf k}} \xi_{\bf k} c^{\dagger}_{\sigma,{\bf
k}}c_{\sigma,{\bf k}}+\sum_{{\bf k}} \Delta_R ( c^{\dagger}_{{\bf
k},\uparrow}c^{\dagger}_{{\bf -k},\downarrow}+ c_{{\bf
k},\downarrow} c_{{\bf -k},\uparrow})
$$
the right side
$$
H_L=\sum_{\sigma,{\bf p}}\xi_{\bf p} d^{\dagger}_{\sigma,{\bf
p}}d_{\sigma,{\bf p}}+\sum_{{\bf p}}
\Delta_L (d^{\dagger}_{{\bf p},\uparrow}d^{\dagger}_{{\bf -p},\downarrow} + d_{{\bf p},\downarrow}d_{{\bf -p},\uparrow})
$$

And finaly the tunneling Hamiltonian,
$$
H_T=\sum_{{\bf k}{\bf p},\sigma}(T_{{\bf k}{\bf
p}}c^{\dagger}_{\sigma,{\bf k}}d_{\sigma,{\bf p}}+T^*_{{\bf k}{\bf
p}}d^{\dagger}_{\sigma,{\bf p}}c_{\sigma,{\bf k}})
$$

We note two things about this tunneling Hamiltonian. First, it is a approximation where the leftside and the right side are assumed to be divided. However, it gives the tunneling rates different from the Fermi's Golden rule when we consider only one level at each side. 

The particle number operator, 
$$
N_R=\sum_{\sigma,{\bf k}}
c^{\dagger}_{\sigma,{\bf k}}c_{\sigma,{\bf k}},
N_L=\sum_{\sigma,{\bf p}} d^{\dagger}_{\sigma,{\bf p}}d_{\sigma,{\bf
p}}
$$
We calculate the **time derivative of the particle number**. Only the term $H_T$ fails to commute with $N_L$,
$$
\dot N_L=i[H,N_L]=i[H_T,N_L] 
=i[\sum_{{\bf k}{\bf p},\sigma}(T_{{\bf
k}{\bf p}}c^{\dagger}_{\sigma,{\bf k}}d_{\sigma,{\bf p}}+T^*_{{\bf
k}{\bf p}}d^{\dagger}_{\sigma,{\bf p}}c_{\sigma,{\bf
k}}),\sum_{\sigma,{\bf p'}} d^{\dagger}_{\sigma,{\bf
p'}}d_{\sigma,{\bf p'}}]
$$
which gives
$$
\dot N_L= i\sum_{{\bf k}{\bf p},\sigma}(T_{{\bf
k}{\bf p}}c^{\dagger}_{\sigma,{\bf k}}d_{\sigma,{\bf p}}-T^*_{{\bf
k}{\bf p}}d^{\dagger}_{\sigma,{\bf k}}c_{\sigma,{\bf p}})
$$


Then the current operator is just the time derivative of the particle operator multiplies electron charge $e$, and the electrical current would be the quantum average of the charge operator,
$$
I(t)=-e \langle \psi(t)|\dot N_L(t)|\psi(t)\rangle=-e\langle\psi|e^{iHt}\dot
N_Le^{-iHt}|\psi\rangle
=-e\langle\psi|e^{iHt}e^{-iH_0t}e^{iH_0t}\dot
N_Le^{-iH_0t}e^{iH_0t}e^{-iHt}|\psi\rangle.
$$
It looks that electric  current is not directly related to any retarded Green functions (as we will show later, it is actually nothing but a specific **lesser** Green function), therefore it is not convenient to apply the Matsubara approach to expand the S-matrix. The solution here is to expand the S-matrix in the time regime first, then go to Mastubara picture later.
We note that the operators are defined in the **Heseinberg representation** now. 
We first  change to the **interaction representation**. We define the evolution operator,
$$
U(t)=e^{iH_0t}e^{-iHt}.
$$
It has a formal solution of the form,
$$
U(t)= T \{{\rm exp}[-i\int_0^t dt_1 \hat H_T(t_1)]\}
$$
where $T$ is the notation for the time ordering of the operators, and $H_T$ is the tunneling Hamiltonian in the interaction representation. Here we note the interesting part of the interaction representation. In Shr\"{o}dinger representation, the Operators $H_T$are time independent and the dynamics is described by the wave function $\psi(t)$. While in the Heseinberg representation the quantum states $\psi$ are time independent and the quantum dynamics is described by the operator evolution $H_T(t)$. However, in the interaction representation, both the operators and the quantum states are time dependent. Therefore, we would have $\hat H_T(t) = e^{iH_0 t} H_T e^{-iH_0 t}$ and $\hat \psi(t) = e^{iH_0 t} e^{-iH t} \psi(0)$ at the same time. **Importantly, we notice that the interaction representation is equivalent to the Heseinberg representation if the perturbation part is 0.** Therefore,  the nonperturbed wave function would have $\hat \phi (t) = \phi_0$.
**Now we show the difference and equivalence of these three representations with a simple example: a two level system with a Hamilton $H= a\sigma_z + b \sigma_x$.**
 


Now we enter the **the core part of the Green function technique.** We could define an $S$-Matrix with the evolution operator,
$$
S(t,t') = U(t) U^\dagger(t')= T {\rm exp}\left[-i\int_{t'}^t dt_1 {\hat H}_T(t_1)\right].
$$
This S-matrix connects the ground state at different times through the relation,
$$
|\hat \psi(t)\rangle=U(t) | \hat \psi(t=0)\rangle=S(t,t')|\hat \psi(t')\rangle
$$
According to the **Gellman-Law theorem[cite Mahan p71]**, the quantum ground state of the system with and without the perturbation are connected by the $S$-Matrix,
$$
|\hat \psi_(t=0) \rangle =T {\rm exp}\left[-i\int_{-\infty}^0 dt' \hat H_T(t')\right] |\phi_0 \rangle = S(0,-\infty) |\phi _0 \rangle.
$$
Here we note that: 1) the Gellman-Law theorem is not exact theorem, in fact, they only prove that the non-interacting ground state will evolve to an eigenstate of the interacting system; and 2) this theorem mathematically states that $|\psi(-\infty) \rangle = |\phi_0 \rangle$. The conceptual adiabatic process of switching on the interaction is not reflected in the formula. 



Now we express the electrical current as,
$$
I(t) =-e \langle  \psi_0|U^{\dagger}(t)e^{iH_0t}\dot
N_Le^{-iH_0t}U(t)|\psi_0 \rangle,
$$
which can be rewritten with S-matrix as,
$$
I(t) =-e \langle  \phi_0|S^{\dagger}(t,-\infty)e^{iH_0t}\dot
N_Le^{-iH_0t}S(t,-\infty)|\phi_0 \rangle.
$$
Now we  only consider linear response, therefore we only take the first order term in the S matrix expansion, which leads to,
$$
S(t,-\infty)|\phi_0 \rangle =\left[1-i\int_{-\infty}^t dt_1 \hat H_T(t_1)\right]|\phi_0 \rangle + O(H_T)^2,
$$
take only the term proportional to $|T_{kp}|^2$ in current,
$$
I(t)=  -e \langle  \phi_0|\left[1+ i\int_{-\infty}^t dt_1 \hat H_T(t_1)\right]e^{iH_0t}\dot
N_Le^{-iH_0t}\left[1-i\int_{-\infty}^t dt_1 \hat H_T(t_1)\right]|\phi_0 \rangle
$$
$$
=-ei\int_{-\infty}^t dt_1 \langle  \phi_0|\left[\dot {\hat N}_L(t),\hat H_T(t_1)\right]|\phi_0 \rangle,
$$
where all the operators are defined in the interaction representation,
$$
\hat H_T(t_1)=e^{iH_0t_1}H_Te^{-iH_0t_1},
$$
and
$$
\frac{\hat{N}_L(t)}{dt}=e^{iH_0t}{\dot N}_Le^{-iH_0t}.
$$
We notice that we obtain an expression for the electrical current within a perturbation scheme. The small perturbation is chosen to be the tunneling Hamiltonian and  its first order is adopted in the expansion of the S-Matrix. After this **approximation**, we has reached to a formula for the current defined by  the correlation function under the un-tunneling Hamiltonian.
This expansion is somehow similar to the **linear response** approximation. We should note that the S-matrix expansion in this approach is not the standard expansion in which we could apply Wick theorem and Dyson equations. That is why we call this linear response. It is because we could not naturally extend the expansion to higher orders and obtain self-energies. In this respect, the Matsubara approach is not as good as the Keldysh formalism when treating mesoscopic ballistic transport phenomenon


Now we should insert the chemical potential, since the it might be different in the two sides of the junction. We now face a tricky non-equilibrium problem. We define,
$$
K_R=H_R-\mu_L N_R=\sum_{\sigma,{\bf k}}(\xi_{\bf k}-\mu_R)
c^{\dagger}_{\sigma,{\bf k}}c_{\sigma,{\bf k}}+\sum_{{\bf k}}
(\Delta c^{\dagger}_{{\bf k},\uparrow}c^{\dagger}_{{\bf
k},\downarrow}+H.C.)
$$

$$K_L=H_L-\mu_L N_L=\sum_{\sigma,{\bf p}}(\xi_{\bf p}-\mu_L)
d^{\dagger}_{\sigma,{\bf p}}d_{\sigma,{\bf p}}+\sum_{{\bf p}}
(\Delta d^{\dagger}_{{\bf p},\uparrow}d^{\dagger}_{{\bf
p},\downarrow}+H.C.),
$$
then we would have
$$
K_0=K_L+K_R,
$$
and the unperturbed Hamiltonian writes as,
$$
H_0=K_0+\mu_L N_L+\mu_R N_R.
$$
With this reformation of the Hamiltonian, the time evolution operator of the unperturbed Hamiltonian is,
$$
e^{iH_0t}=e^{iK_0t}\cdot e^{i(\mu_L N_L+\mu_R N_R)t},
$$
thus the time development of the tunneling Hamiltonian $H_T$, i.e. the tunneling Hamiltonian in the interaction representation, is expressed as,
$$
\hat H_T(t_1) =e^{iH_0t_1}H_Te^{-iH_0t_1}
$$

$$=e^{iK_0t_1}\left(e^{i(\mu_L N_L+\mu_R
N_R)t_1}H_Te^{-i(\mu_L N_L+\mu_R N_R)t_1}\right)e^{-iK_0t_1}
$$

$$
=e^{iK_0t_1}\left(\sum_{{\bf k},{\bf p},\sigma}\left(T_{{\bf k},{\bf p}} e^{it_1(\mu_R-\mu_L)}c^{\dagger}_{\sigma,{\bf k}}d_{\sigma,{\bf
p}}+T^*_{{\bf k}{\bf p}}e^{it_1(\mu_L-\mu_R)}d^{\dagger}_{\sigma,\bf
p} c_{\sigma, \bf k}\right)\right)e^{-iK_0t_1},
$$

$$
= \sum_{{\bf k},{\bf p},\sigma}\left(T_{{\bf k},{\bf p}} e^{it_1(\mu_R-\mu_L)} \hat c^{\dagger}_{\sigma,{\bf k}} \hat d_{\sigma,{\bf
p}}+T^*_{{\bf k}{\bf p}}e^{it_1(\mu_L-\mu_R)} \hat d^{\dagger}_{\sigma,\bf
p} \hat c_{\sigma, \bf k}\right),
$$

where  $\hat c_{\bf k}(t)=e^{i K_L t}c_{\bf k}e^{-i K_L t}$ and $\hat d_{\bf
p}(t)=e^{i K_R t}d_{\bf p}e^{-i K_R t}$ are the operators in the {\pb interaction representation with  chemical potentials}. In the derivation we use the relations,

$$
[c^{\dagger}_{{\bf k}}c_{{\bf k}},c^{\dagger}_{{\bf
k}}]=c^{\dagger}_{{\bf k}};[c^{\dagger}_{{\bf k}}c_{{\bf k}},c_{{\bf
k}}]=-c_{{\bf k}}
$$

$$
e^{it \mu c^{\dagger}_{{\bf k}}c_{{\bf k}}}c^{\dagger}_{{\bf
k}}e^{-it \mu c^{\dagger}_{{\bf k}}c_{{\bf k}}}=e^{it
\mu}c^{\dagger}_{{\bf k}}
$$

$$
e^{it \mu c^{\dagger}_{{\bf k}}c_{{\bf
k}}}c_{{\bf k}}e^{-it \mu c^{\dagger}_{{\bf k}}c_{{\bf k}}}=e^{-it
\mu}c_{{\bf k}}
$$

$$
e^{it \mu {\hat N}}c^{\dagger}_{{\bf k}}e^{-it \mu {\hat N}}=e^{it
\mu}c^{\dagger}_{{\bf k}}
$$

$$
e^{it \mu {\hat N}}c_{{\bf k}}e^{-it \mu {\hat N}}=e^{-it
\mu}c_{{\bf k}}.
$$
For the operator $\dot {\hat N}$, we could perform the same calculation and obtain similar results. In the tunneling problem, the difference between the chemical potentials of the two side are provided by the applied voltage, therefore we define $\mu_L-\mu_R=eV$
and the current can be expressed as,
$$
I(t)=- i^2 e \int_{-\infty}^{t} dt_1  \langle \sum_{{\bf {\bf k}}{\bf {\bf
p}},\sigma} \left[T_{{\bf k}{\bf p}}e^{-ieVt} \hat c^{\dagger}_{{\bf k}} (t)
\hat d_{{\bf p}}(t)-T^{*}_{{\bf k}{\bf p}} e^{ieVt} \hat d^{\dagger}_{{\bf p}}(t) \hat c_{{\bf k}}(t)\right],
$$

$$
\sum_{{\bf {\bf k}'}{\bf {\bf p}'},\sigma} \left[T_{{\bf k}'{\bf
p}'}e^{-ieVt_1} \hat c^{\dagger}_{{\bf k}'} (t_1) \hat d_{{\bf
p}'}(t_1)-T^{*}_{{\bf k}'{\bf p}'} e^{ieVt_1} \hat d^{\dagger}_{{\bf
p}'}(t_1) \hat c_{{\bf k}'}(t_1)\right]  \rangle_0.
$$
We notice that the operators $H_T$ and $\dot N$ are the real and imaginary part of the same operator, therefore, we could simplify the problem with a definition of,
$$
A(t)= \sum_{\bf k p,\sigma} T_{\bf k p} \hat c_{\sigma,\bf
k}^{\dagger}(t) \hat d_{\sigma,\bf p}(t).
$$
With this new operator, the old two operators are expressed as,
$$
\dot{\hat N}_L(t)=i[e^{-ieVt}A(t)-e^{ieVt}A^{\dagger}(t)],
$$
and
$$
\hat H_T(t_1)=e^{-ieVt}A(t_1)+e^{ieVt}A^{\dagger}(t_1).
$$
Then the current is expressed as,
$$
I(t)=e \int_{-\infty}^{\infty} dt_1 \Theta(t-t_1)
\{e^{ieV(t_1-t)} \langle  [A(t),A^{\dagger}(t_1)] \rangle_0 -e^{ieV(t-t_1)} \langle  [A^{\dagger}(t),A(t_1)] \rangle_0 $$

$$
+
e^{-ieV(t_1+t)} \langle  [A(t),A(t_1)] \rangle_0 -e^{ieV(t+t_1)} \langle  [A^{\dagger}(t),A^{\dagger}(t_1)] \rangle_0 \},
$$

where $\Theta(t-t_1)$ is the step function.
Now we can divide the current into the the single particle tunneling current,
$$
I_s(t)=e \int_{-\infty}^{\infty} dt_1 \Theta(t-t_1)
\left[e^{ieV(t_1-t)} \langle  [A(t),A^{\dagger}(t_1)] \rangle_0 -e^{ieV(t-t_1)} \langle  [A^{\dagger}(t),A(t_1)] \rangle_0 
\right],
$$

and Josephson current,
$$
I_J(t)=e \int_{-\infty}^{\infty} dt_1 \Theta(t-t_1) \{
e^{-ieV(t_1+t)} \langle  [A(t),A(t_1)] \rangle_0 -e^{ieV(t+t_1)} \langle  [A^{\dagger}(t),A^{\dagger}(t_1)] \rangle_0 \}. 
$$


## Single Particle Current

For the single particle current, we obtain a simple {\pb retarded Green function form, which could be calculated using the Masubara Green function technique.} We notice that the integration in the current is a function of $t-t_1$, therefore, the current is time independent. We set $t_1 = 0$ and change the integration to $t$ and could obtain,
$$
I_s(t=0) =e \int_{-\infty}^{\infty} dt_1 \Theta(-t_1)
\left[e^{ieVt_1} \langle  [A(0),A^{\dagger}(t_1)] \rangle_0 -e^{-ieV t_1} \langle  [A^{\dagger}(0),A(t_1)] \rangle_0 
\right],
$$
$$
= - e \int_{\infty}^{-\infty} dt \Theta(t)
\left[e^{-ieVt} \langle  [A(0),A^{\dagger}(-t)] \rangle_0 -e^{ieV t} \langle  [A^{\dagger}(0),A(-t)] \rangle_0  
\right],
$$
$$
= e \int_{-\infty}^{\infty} dt \Theta(t)
\left[e^{-ieVt} \langle  [A(t),A^{\dagger}(0)] \rangle_0 -e^{ieV t} \langle  [A^{\dagger}(t),A(0)] \rangle_0  
\right],
$$

$$
=e 
\int_{-\infty}^{\infty} dt e^{-ieVt}   \Theta(t) \langle  [A(t),A^{\dagger}(0)] \rangle_0 -e \int_{-\infty}^{\infty} dt e^{ieV t}   \Theta(t) \langle  [A^{\dagger}(t),A(0)] \rangle_0.
$$

$$
=  e 
\int_{-\infty}^{\infty} dt e^{-ieVt}   \Theta(t) \langle  [A(t),A^{\dagger}(0)] \rangle_0 +e \int_{-\infty}^{\infty} dt e^{-ieV t}   \Theta(-t) \langle  [A(t),A^\dagger(0)] \rangle_0.
$$

Now we define the retarded and advanced Green function,
$$
U_{ret}(t)=-i \theta(t)  \langle  [A(t),A^\dagger(0)] \rangle_0. 
$$

$$
U_{adv}(t)= i \theta(-t)  \langle  [A(t),A^\dagger(0)] \rangle_0. 
$$
Then the current could be rewritten as a {\pb Fourier transformation} of the Green function,  
$$
I_s =i e 
\left( \int_{-\infty}^{\infty} dt e^{-ieVt}  U_{ret}(t) -  \int_{-\infty}^{\infty} dt e^{-ieV t}    U_{adv}(t) \right).
$$


$$
= ie \left( U_{ret} (-eV) - U_{adv} (-eV) \right)
$$

$$
= 2e {\rm Im} U_{ret} (-eV)
$$
Now we calculate this current to obtain the conductivity. We begin from the Mastubara formalism. The Matsubara Green function is defined as,
$$
\mathscr{U}(i\omega)  = - \int_0^\beta d\tau  e^{i\omega \tau}   \langle T_\tau A(\tau) A^\dagger(0) \rangle_0
$$
$$
=- \sum_{k,p,\sigma} \sum_{k',p',\sigma'} T_{k,p} T^*_{k',p'}  \int_0^\beta d\tau  e^{i\omega \tau}  \langle T_\tau \hat c^\dagger_\sigma(k,\tau) \hat d_\sigma(p,\tau) \hat d^\dagger_{\sigma'}(p',0) \hat c_{\sigma'}(k',0) \rangle_0
$$
$$
= \sum_{k,p,\sigma}  |T_{k,p}|^2 \int_0^\beta d\tau  e^{i\omega \tau}  \langle T_\tau \hat c_{\sigma}(k,0)  \hat c^\dagger_\sigma(k,\tau) \rangle \langle_0 T_\tau  \hat d_\sigma(p,\tau) \hat d^\dagger_{\sigma}(p,0)  \rangle_0
$$
$$
=\sum_{k,p,\sigma}  |T_{k,p}|^2 \int_0^\beta d\tau  e^{i\omega \tau}   \mathscr{G}^{(0)}_L(k,-\tau)  \mathscr{G}^{(0)}_R(p,\tau)
$$
$$
=\sum_{k,p,\sigma}  |T_{k,p}|^2 \frac{1}{\beta } \sum_{ip}  \mathscr{G}^{(0)}_L(k,ip-i\omega)  \mathscr{G}^{(0)}_R(p,ip).
$$
**Here we notice that the operators are averaged over the non-interacting ground states, the reason is that the S-matrix expansion has been done previously. Thereby we use the green function $\mathscr{G}^{(0)}$ to represents the -----bare-- Green function for the system --without-- electron tunneling and interaction.** For a normal system, the imaginary frequency summation can be performed by the standard method using the residue theorem, which gives,
$$
\mathscr{U}(i\omega) = \sum_{k,p,\sigma}  |T_{k,p}|^2 \frac{1}{\beta } \sum_{ip} \frac{1}{ip-i\omega-\xi_{\bf k}} \frac{1}{ip-\xi_{\bf p}}
$$
$$
= \sum_{k,p,\sigma}  |T_{k,p}|^2  \left(\frac{n_F(\xi_{\bf p})}{\xi_{\bf p} -i\omega -\xi_{\bf k}} + \frac{n_F(i\omega+\xi_{\bf k})}{i\omega+\xi_{\bf k} -\xi_{\bf p}}\right)
$$
$$
=  \sum_{k,p,\sigma}  |T_{k,p}|^2  \frac{n_F(i\omega+\xi_{\bf k})- n_F(\xi_{\bf p})}{i\omega+\xi_{\bf k} -\xi_{\bf p}}
$$
$$
=  \sum_{k,p,\sigma}  |T_{k,p}|^2  \frac{n_F(\xi_{\bf k})- n_F(\xi_{\bf p})}{i\omega+\xi_{\bf k} -\xi_{\bf p}}.
$$
Therefore the current is expressed as,
$$
I  = 2e {\rm Im} U_{ret} (eV) 
$$
$$
= 4 \pi e  \sum_{k,p,\sigma}  |T_{k,p}|^2  \left( n_F(\xi_{\bf k})- n_F(\xi_{\bf p}) \right)  \delta(-eV   +\xi_{\bf k} -\xi_{\bf p}),
$$
where we use the formula of**[citation needed]**,
$$
\frac{1}{\omega + i \delta - \xi_{\bf k}} = P\frac{1}{\omega + i \delta - \xi_{\bf k}} + 2\pi i   \delta (\omega - \xi_{\bf k}).
$$
We notice that we have an interesting $\delta$ function in the expression for the current. This $\delta$ function guarantees that the tunneling between two states with different energy does not contribute to the current. This $\delta$ function is actually the spectrum function of the bare system. This formula should understood in the sense of the integration, where the **residue theorem** could prove the equality. 




 
Now we calculate the summation analytically. Since the major contribution to the current should be around the Fermi surface when the voltage is small, we simply assume that the density of the states are constant, whose values are taken at the two Fermi surfaces. There for, we could transform the summation over momentum to the integration over the energy,
$$
\sum_{k} \longrightarrow \int \frac{dk}{(2\pi)^3} \longrightarrow  N_L \int d \xi_{\bf k}
$$

$$
\sum_{p} \longrightarrow  \int \frac{dp}{(2\pi)^3} \longrightarrow  N_R \int d \xi_{\bf p}.
$$

Then the summation for the current is rewritten to,

$$
I  = 4 \pi e N_L N_R |T|^2  \int \int  d \xi_{\bf k} d \xi_{\bf p}    \left( n_F(\xi_{\bf k})- n_F(\xi_{\bf p}) \right)  \delta(-eV   +\xi_{\bf k} -\xi_{\bf p}),
$$
$$
= 4 \pi e N_L N_R |T|^2  \int d \xi_{\bf p}  \left( n_F(\xi_{\bf p} + eV)- n_F(\xi_{\bf p}) \right).
$$
For zero temperature, the Fermi distribution function becomes step function, then the formula could be integrated out as,
$$
I  = 4 \pi e N_L N_R |T|^2  \int   d \xi_{\bf p}  \left( \Theta(-\xi_{\bf p} - eV) - \Theta (-\xi_{\bf p}) \right)
$$
$$
= 4 \pi e N_L N_R |T|^2  \int_{-eV}^0   d \xi_{\bf p} 
$$
$$
= 4 \pi e^2 N_L N_R |T|^2 V \equiv \sigma_0 V,
$$
with the normal conductance,
$$
 \sigma_0 =4 \pi e^2 N_L N_R |T|^2.
$$
Now we consider interaction in the two electrodes. In this case, the Green function of the left and right side are **NOT simple bare electron Green function**. We have to include the interaction with a spectra function.
$$
\mathscr{U}(i\omega)  =\sum_{k,p,\sigma}  |T_{k,p}|^2 \frac{1}{\beta } \sum_{ip}  G^0_L(k,ip-i\omega)  G^0_R(p,ip).
$$

$$
= \sum_{k,p,\sigma}  |T_{k,p}|^2   \int d\epsilon_1 A(k,\epsilon_1 )    \int d\epsilon_2 A(p,\epsilon_2)      \frac{1}{\beta } \sum_{ip} \frac{1}{ip - i\omega -\epsilon_1} \frac{1}{ip-\epsilon_2}
$$
$$
= \sum_{k,p,\sigma}  |T_{k,p}|^2   \int d\epsilon_1 A(k,\epsilon_1 )    \int d\epsilon_2 A(p,\epsilon_2)     \frac{n_F(\epsilon_1)- n_F(\epsilon_2)}{i\omega+\epsilon_1 - \epsilon_2}.
$$
**Here the Green function $G^0$ represents the Green function with the interaction in the lead but without the electron tunneling between two leads.** The current is obtained through the analytic continuation of $i\omega \rightarrow eV+ i\delta$,
$$
I = 2e {\rm Im} \mathscr{U}(\omega +  i\delta)
$$
$$
= 4\pi e \sum_{k,p,\sigma}  |T_{k,p}|^2   \int d\epsilon_1 A(k,\epsilon_1 )    \int d\epsilon_2 A(p,\epsilon_2)     \left[ n_F(\epsilon_1)- n_F(\epsilon_2)\right] \delta(eV+\epsilon_1 - \epsilon_2) 
$$
$$
= 4\pi e \sum_{k,p,\sigma}  |T_{k,p}|^2   \int d\epsilon_1 A(k,\epsilon_1 )    A(p,\epsilon_1+ eV)     \left[ n_F(\epsilon_1)- n_F(\epsilon_1+ eV)\right]
$$
These calculation brings the exact results of Schrieffer. If the tunneling matrix can be approximated as a constant $T_{k,p}=T$, then the summation over the momentum is just the density of states,
$$
I = 4\pi e  |T|^2     \int d\epsilon_1  \sum_{k,p,\sigma}  A(k,\epsilon_1 )    A(p,\epsilon_1+ eV)     \left[ n_F(\epsilon_1)- n_F(\epsilon_1+eV)\right]
$$
$$
=  4\pi e  |T|^2     \int d\epsilon_1 N_L(\epsilon_1)    N_R (\epsilon_1+ eV)     \left[ n_F(\epsilon_1)- n_F(\epsilon_1+ eV)\right]
$$
$$
\approx  4\pi e  |T|^2  N_L N_R   \int d\epsilon_1   \left[ n_F(\epsilon_1)- n_F(\epsilon_1+ eV)\right]
$$
This formula is the final result for the current from the single particle tunneling processes. We derive this formula directly from the single particle Green function. Therefore,this result is a general result for the single particle tunneling between any two system, including normal metals, superconductors, semiconductors, etc, as long as we correctly adopt the  spectra functions in the formula. We could also obtain this result through the **quantum mechanics approach**. In this method[cite datta], the current is divided into the component from the left to the right,
$$
I_1  = 4\pi e \sum_{k,p,\sigma}  |T_{k,p}|^2   \int d\epsilon_1 A(k,\epsilon_1 ) A(p,\epsilon_1+ eV ) n_F (\epsilon_1) \left[ 1- n_F(\epsilon_1 + eV) \right]
$$
$$
=  4\pi e  |T|^2  N_L N_R  \int d\epsilon_1 n_F (\epsilon_1) \left[ 1- n_F(\epsilon_1 + eV) \right],
$$
and the current from the right to the left,
$$
I_2 =4\pi  e \sum_{k,p,\sigma}  |T_{k,p}|^2   \int d\epsilon_1 A(k,\epsilon_1 ) A(p,\epsilon_1+ eV ) n_F (\epsilon_1+eV) \left[ 1- n_F(\epsilon_1 ) \right]
$$
$$
=  4\pi e  |T|^2  N_L N_R  \int d\epsilon_1 n_F (\epsilon_1+eV) \left[ 1- n_F(\epsilon_1) \right].
$$
This formula is much more intuitive, since it decries the current after the cancellation of two quantum tunneling processes.