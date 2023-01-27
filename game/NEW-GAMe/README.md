# NEW GAME
<app-header></app-header>

<div *ngIf="gameMode === 'intro-1'" class="dashboard-container">
	<div class="video-div">
		<video class="intro-video" id="intro-video" (ended)="playDay1IntroVideos()" autoplay="autoplay">
			<source class="active" type="video/mp4" src="assets/videos/introduction/day1/Intro_1.mp4"/>
		</video>
	</div>
</div>

<div *ngIf="gameMode === 'intro-2'" class="dashboard-container">
	<div class="video-div">
		<video class="intro-video" id="intro-video" (ended)="playDay2IntroVideos()" autoplay="autoplay">
			<source class="active" type="video/mp4" src="assets/videos/introduction/day2/Intro_1.mp4"/>
		</video>
	</div>
</div>

<div *ngIf="gameMode === 'intro-gender'" class="container dashboard-container">
	<div class="gender-div" id="gender-div">
		<span class="female-pirate">
			<label class="pirate-gender-radio-label">
				<input type="radio" name="pirate" value="f" [(ngModel)]="pirateGender"/>
				<img src="assets/images/pirate-characters/female-pirate.png" />
			</label>
		</span>
		
		<span class="male-pirate">
			<label class="pirate-gender-radio-label">
				<input type="radio" name="pirate" value="m" [(ngModel)]="pirateGender"/>
				<img src="assets/images/pirate-characters/male-pirate.png" />
			</label>
		</span>

		<div class="clear container">
			<button type="button" id="next-btn" class="next-btn btn btn-success" (click)="clickNextBtn()" [disabled]="!pirateGender">Next</button>
		</div>
	</div>
</div>

<div *ngIf="gameMode === 'intro-pirates'" class="dashboard-container">
	<div class="pirates-div" id="pirates-div">
		<span *ngFor="let option of pirateOptions">
			<label class="pirate-character-label">
				<input type="radio" name="pirate-option" value="{{option}}" [(ngModel)]="pirateCharacter" />
				<img src="assets/images/pirate-characters/{{option}}.png" />
			</label>
		</span>
		
	</div>

	<div class="clear container">
		<button type="button" id="next-btn" class="next-btn btn btn-success" (click)="clickNextBtn()" [disabled]="!pirateCharacter">Next</button>
	</div>
</div>

<div *ngIf="gameMode === 'intro-after-pirates'" class="dashboard-container">
	<div id="great-choice-div">
		<img src="assets/images/pirate-characters/{{pirateCharacter}}.png" />
		<img src="assets/images/pirate.png" style="float:right;" width="50%"/>
	</div>

	<div id="intro-continue-div" class="intro-continue-div">			
		<video class="intro-continue" id="intro-continue" (ended)="playContinueVideos()">
			<source type="video/mp4" />
		</video>
	</div>
	<div>
		<button type="button" id="start-game-btn" class="start-game-btn btn btn-success" (click)="startGameBtn()" >Start</button>
	</div>

	<div id="intro-end-div" class="intro-end-div">
		<img src="assets/images/pirate.png" width="50%"/>

		<div>
			<button type="button" id="start-game-btn" class="start-game-btn btn btn-success" (click)="startGameBtn()" >Start</button>
		</div>
	</div>
</div>

<div *ngIf="gameMode === 'intro2-gender'" class="container dashboard-container">
		<div class="gender-div" id="gender-div">
			<span class="female-pirate">
				<label class="pirate-gender-radio-label">
					<input type="radio" name="pirate" value="f" [(ngModel)]="pirateGender"/>
					<img src="assets/images/pirate-characters/female-pirate.png" />
				</label>
			</span>
			
			<span class="male-pirate">
				<label class="pirate-gender-radio-label">
					<input type="radio" name="pirate" value="m" [(ngModel)]="pirateGender"/>
					<img src="assets/images/pirate-characters/male-pirate.png" />
				</label>
			</span>
	
			<div class="clear container">
				<button type="button" id="next-btn" class="next-btn btn btn-success" (click)="clickNextBtn2()" [disabled]="!pirateGender">Next</button>
			</div>
		</div>
	</div>
	
	<div *ngIf="gameMode === 'intro2-pirates'" class="dashboard-container">
		<div class="pirates-div" id="pirates-div">
			<span *ngFor="let option of pirateOptions">
				<label class="pirate-character-label">
					<input type="radio" name="pirate-option" value="{{option}}" [(ngModel)]="pirateCharacter" />
					<img src="assets/images/pirate-characters/{{option}}.png" />
				</label>
			</span>
			
		</div>
	
		<div class="clear container">
			<button type="button" id="next-btn" class="next-btn btn btn-success" (click)="clickNextBtn2()" [disabled]="!pirateCharacter">Next</button>
		</div>
	</div>
	
	<div *ngIf="gameMode === 'intro2-after-pirates'" class="dashboard-container">
		<div id="great-choice-div">
			<img src="assets/images/pirate-characters/{{pirateCharacter}}.png" />
			<img src="assets/images/pirate.png" style="float:right;" width="50%"/>
		</div>
	
		<div id="intro-continue-div" class="intro-continue-div">			
			<video class="intro-continue" id="intro-continue" (ended)="playContinueVideos()">
				<source type="video/mp4" />
			</video>
		</div>

		<div>
			<button type="button" id="start-game-btn" class="start-game-btn btn btn-success" (click)="startGame2Btn()" >Start</button>
		</div>
	
		<div id="intro-end-div" class="intro-end-div">
			<img src="assets/images/pirate.png" width="50%"/>
	
			
		</div>
	</div>

<div *ngIf="gameMode === 'game'" class="container dashboard-container">
	
	<div class="row">
		<br/>
	</div>

	<div class="row" style="margin: 150px auto 0;">
		<div class="col-6 text-center">
			<button type="button" id="day1-btn" class="day1-btn btn btn-success" (click)="goToDay1Games()">PARROT</button>
		</div>

		<div class="col-6 text-center">
			<button type="button" id="day2-btn" class="day1-btn btn btn-success" (click)="goToDay2Games()">PALM TREE</button>
		</div>
	</div>
</div>

<div *ngIf="gameMode === 'game-day1' || gameMode === 'game-day2'" class="container dashboard-container" style="margin: 150px auto 0;">
	<div class="row">
		<button class="btn btn-link" (click)="backToGame()">&lt;&lt;Previous</button>
	</div>

	<div class="row">
		<br/>
	</div>

	<div class="row">
		<div *ngFor="let gameId of gameIds" class="col-sm-6" style="margin-bottom: 5px;">
			<span *ngIf="listOfGames[gameId].order != ''" class="btn btn-secondary game-btn">
				{{listOfGames[gameId].name}}  ({{listOfGames[gameId].order}})
			</span>
			<a *ngIf="listOfGames[gameId].order == ''" class="btn btn-success game-btn" [routerLink]="listOfGames[gameId].link">
				{{listOfGames[gameId].name}} 
			</a>
		</div>
	</div>

	<div class="row">
		<br/>
	</div>

	<div class="row">
		<div *ngIf="showGameStore" class="col-12 text-right">
			<a class="btn btn-success" [routerLink]="['/app/store']">Go to Store</a>
		</div>
	</div>
</div>