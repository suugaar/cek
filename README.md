<?php
if(isset($_POST['submit']))
{	
?>
<div class="container"> 
	<div class="hasil"> 
		<h3>Hasil</h3>
		<table width="100%" align='center' border='1'>
			

			<?php

			$atas = $_POST['atas'];
			$bawah = $_POST['bawah'];
			$pembagi = $_POST['pembagi'];

			$nilaiH = ($atas + $bawah)/$pembagi;
			echo "<td colspan='2'><strong>NILAI H = ".$nilaiH."</trong></td>";
			echo "<tr>
				<th>Nilai x</th>
				<th>Nilai f(x)</th>
			</tr>";
			$x = $bawah;
			$nk = 0; // nilai yang di kali dengan 2 berdasarkan rumus
			$ntk = 0; //nilai pertama dan terakhir
			for($i=0;$i<=$pembagi;$i++)
			{
				echo "<tr>";
				if($i == 0)
				{
					$x = $x; //nilai x awal sebelum di tambah nilai H
				}
				else
				{
					$x = $x + $nilaiH; // nilai x yang di tambah dengan nilai h
				}
				
				$fx = $x*$x; // untuk mencari nilai f(x)
				
				if(($i != 0) && ($i != $pembagi))
				{
					$nk = $nk + $fx; //menambahkan nilai x selain nilai awal dan terakhir
				}
				else
				{
					$ntk = $ntk+ $fx; // menambahkan nilai awal dan terakhir
					
				}
				
				echo "<td align='center'>".$x."</td><td align='center'>".$fx."</td>";
				echo "</tr>";
			}
			$hasil = ($nilaiH/2)*(($nk*2)+$ntk);
			echo "<tr>";
			echo "<td colspan='2' align='center'>LUAS ".$hasil."</td>";
			echo "</tr>";
			?>
		</table>
	</div>
</div>
<?php
}  
 ?>
